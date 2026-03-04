---
layout:     post
title:      "Decoding Mouse Maze Position from Brain Signals"
subtitle:   "A 48-hour proof of concept at Hacktion Potential"
date:       2026-03-02 12:00:00
author:     "Clement Wang"
catalog: true
published: true
tags:
    - Hackathon
    - Neuroscience
    - Computational Neuroscience
    - Time series analysis
---

Last weekend I took part in **[Hacktion Potential](https://www.hacktionpotential.fr/)**, a 48-hour computational neuroscience hackathon at the **Institut du Cerveau** in Paris. Our team worked on decoding **mouse maze position from brain signals**: mapping high-dimensional neural activity to the (x,y) position of a mouse in a closed environment.

The hackathon goal was to design a decoding method that takes raw hippocampal data (spike activity recorded at ~20 kHz) and predicts spatial location.

![Trajectory](https://github.com/clementw168/mouse-maze-position-from-brain-signals/raw/main/assets/trajectory/trajectory_trail.gif)

## Technical story

Since we had very limited time, we kept the approach simple: 1D-CNNs, a few ablations, and a focus on understanding the data and evaluation (splits, window size) rather than pushing state-of-the-art architectures.

### Data

Recordings come from the hippocampus (CA1) with a silicon probe at 20 kHz. Each probe has several shanks recording from different locations. For each decoding timepoint we have the true (x,y) position (in seconds or in indices at ~15 Hz). Only timepoints where the mouse is moving are used for decoding, since position encoding is physiologically only relevant during movement.

The dataset is built from **highpass-filtered, spike-focused** activity. For each shank we: detect spikes when voltage exceeds 3× standard deviation on any channel.

![Spike visualization](/img/posts/2026/hacktion_data.png)

### Model architecture and data ablation

We tested whether **spike waveforms** are needed for decoding. Two models:

- **Spiking Embedding Network**: only the sequence of spike indices (which shank fired). Trainable embeddings per shank → sequence → 1D-CNN → FC → (x,y).
- **Waveform Network**: 1D-CNN on the actual waveforms, then global average pooling over the sequence → FC → (x,y).

<style>
.img-row-2 {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 15px;
  margin: 20px 0;
}
.img-row-2 img { width: 100%; height: auto; display: block; border-radius: 6px; }
.img-row-2 figure { margin: 0; }
.img-row-2 figcaption { text-align: center; font-size: 0.9em; color: #666; margin-top: 8px; }
@media (max-width: 768px) { .img-row-2 { grid-template-columns: 1fr; } }
</style>

<div class="img-row-2">
  <figure>
    <img src="/img/posts/2026/spiking_embedding_net.png" alt="Spiking Embedding Network">
    <figcaption>Spiking Embedding Network</figcaption>
  </figure>
  <figure>
    <img src="/img/posts/2026/waveform_net.png" alt="Waveform Network">
    <figcaption>Waveform Network</figcaption>
  </figure>
</div>

<div class="img-row-2">
  <figure>
    <img src="https://github.com/clementw168/mouse-maze-position-from-brain-signals/raw/main/assets/spike_vs_waveform/losses_spikingemb_shuffled_split.png" alt="Losses Spiking Embedding Network">
    <figcaption>Spiking Embedding — train vs test loss</figcaption>
  </figure>
  <figure>
    <img src="https://github.com/clementw168/mouse-maze-position-from-brain-signals/raw/main/assets/spike_vs_waveform/losses_waveform_shuffled_split.png" alt="Losses Waveform Network">
    <figcaption>Waveform — train vs test loss</figcaption>
  </figure>
</div>

Result: the Spiking Embedding Network does not generalize (low train loss, high test loss). The Waveform Network generalizes well. So waveform information appears necessary, likely because it identifies *which* neuron fired, not only *when*. All of this was with a random train/test split.

### Window size

We varied the spike window length (18+18, 54+54, 126+126 timesteps around the peak), i.e. 36, 108, and 252 timesteps. All settings learn; 108 converged fastest, consistent with a trade-off between information and noise.

<div class="img-row-2">
  <figure>
    <img src="https://github.com/clementw168/mouse-maze-position-from-brain-signals/raw/main/assets/window_size/losses_waveform_shuffled_36.png" alt="Window 36">
    <figcaption>Window 36</figcaption>
  </figure>
  <figure>
    <img src="https://github.com/clementw168/mouse-maze-position-from-brain-signals/raw/main/assets/window_size/losses_waveform_shuffled_108.png" alt="Window 108">
    <figcaption>Window 108</figcaption>
  </figure>
</div>
<div class="img-row-2">
  <figure>
    <img src="https://github.com/clementw168/mouse-maze-position-from-brain-signals/raw/main/assets/window_size/losses_waveform_shuffled_252.png" alt="Window 252">
    <figcaption>Window 252</figcaption>
  </figure>
  <figure>
    <img src="https://github.com/clementw168/mouse-maze-position-from-brain-signals/raw/main/assets/window_size/losses_waveform_temporal_108.png" alt="Temporal split, window 108">
    <figcaption>Temporal split, window 108</figcaption>
  </figure>
</div>

<div class="img-row-2">
  <figure>
    <img src="https://github.com/clementw168/mouse-maze-position-from-brain-signals/raw/main/assets/splits/losses_waveform_mid_split.png" alt="Middle split">
    <figcaption>Middle split</figcaption>
  </figure>
  <figure>
    <img src="https://github.com/clementw168/mouse-maze-position-from-brain-signals/raw/main/assets/splits/losses_waveform_temporal_split.png" alt="Temporal split">
    <figcaption>Temporal split</figcaption>
  </figure>
</div>
<div class="img-row-2">
  <figure>
    <img src="https://github.com/clementw168/mouse-maze-position-from-brain-signals/raw/main/assets/splits/losses_waveform_shuffled_split.png" alt="Shuffled split">
    <figcaption>Shuffled split</figcaption>
  </figure>


### Splitting issues

Train/test split had a large impact. We compared:

- **Temporal**: train on first 90%, test on last 10% (as suggested).
- **Middle**: test on middle 10%, train on the rest.
- **Shuffled**: random split.

| Split type    | Lowest train MSE | Lowest test MSE |
|---------------|------------------|-----------------|
| Temporal      | 0.018            | 0.103           |
| Middle        | 0.030            | 0.081           |
| Shuffled      | 0.036            | 0.054           |

Temporal and middle splits generalize poorly; shuffled generalizes better. That points to **distribution shift or non-stationarity** over the session (e.g. electrode drift, fatigue, or the mouse learning the maze) rather than simple data leakage. It does not rule out that the data still carries position information (e.g. Zhang et al., 1998, J Neurophysiol).

<figure>
  <img src="https://github.com/clementw168/mouse-maze-position-from-brain-signals/raw/main/assets/trajectory/prediction_visualization.gif" alt="Prediction visualization">
  <figcaption>Predictions on test (middle split)</figcaption>
</figure>

Predictions on the test set are noisy but follow the trajectory; the model often predicts positions outside the maze.

### Future directions

- **Model**: tune hyperparameters, regularization, data augmentation, cleaner preprocessing to reduce overfitting and shift.
- **Generalization**: run on multiple mice (current runs are one mouse).
- **Multi-subject**: train on pooled data across mice.
- **Model redesign**: condition on maze geometry (e.g. ControlNet-style), predict position as a heatmap, or add past positions as input.

![Key points detection heatmaps](/img/posts/2026/keypoints_detection_heatmaps.png)

## Conclusion

We didn’t win, and the experiments weren’t conclusive—expected when exploring a new dataset in two days. I was glad to get back into neuroscience and to work at that pace; the experience was very stimulating.

- **Repository**: [github.com/clementw168/mouse-maze-position-from-brain-signals](https://github.com/clementw168/mouse-maze-position-from-brain-signals)
- **Slides**: [presentation.pdf](https://github.com/clementw168/mouse-maze-position-from-brain-signals/blob/main/assets/presentation.pdf) in the repo
