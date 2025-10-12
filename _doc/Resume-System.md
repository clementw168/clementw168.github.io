# Resume System Documentation

## Overview

The resume system has been completely refactored to separate content from layout, making it much easier to maintain and edit. The system uses Jekyll's data files and includes to create a modular, maintainable structure.

## File Structure

```
_data/
  resume.yml                 # All resume content in YAML format

_layouts/
  resume.html               # Main resume layout template

_includes/resume/
  header.html              # Personal info and contact details
  education.html           # Education section
  experience.html          # Professional experience
  highlights.html          # Notable achievements and projects
  skills.html              # Technical skills
  languages.html           # Language proficiencies

resume.html                # Main resume page (uses resume layout)
```

## How to Edit Your Resume

### 1. Update Personal Information
Edit `_data/resume.yml` and modify the `personal_info` section:

```yaml
personal_info:
  name: "Your Name"
  title: "Your Title"
  email: "your.email@example.com"
  location: "Your Location"
  github: "https://github.com/yourusername"
  linkedin: "https://linkedin.com/in/yourprofile"
  pdf_download: "/assets/posts/your_resume.pdf"
```

### 2. Add/Edit Education
In the `education` section of `_data/resume.yml`:

```yaml
education:
  - degree: "Degree Name"
    period: "Start Year - End Year"
    institution: "Institution Name"
    description: "Description of your studies"
    supervisor: "Supervisor Name"  # Optional
    supervisor_url: "https://supervisor.url"  # Optional
```

### 3. Add/Edit Experience
In the `experience` section:

```yaml
experience:
  - title: "Job Title"
    period: "Start Date - End Date"
    company: "Company Name"
    description: "Job description"
    achievements:  # Optional
      - "Achievement 1"
      - "Achievement 2"
    post_link: "/path/to/detailed/post/"  # Optional
    post_text: "Read more about this project →"  # Optional
```

### 4. Add/Edit Highlights
In the `highlights` section:

```yaml
highlights:
  - title: "Achievement Title"
    period: "Year"
    organization: "Organization"
    description: "Description of the achievement or project"
    post_link: "/path/to/detailed/post/"  # Optional
    post_text: "Read more →"  # Optional
```

### 5. Update Skills
In the `skills` section:

```yaml
skills:
  - title: "Skill Category"
    items:
      - "Skill 1"
      - "Skill 2"
      - "Skill 3"
```

### 6. Update Languages
In the `languages` section:

```yaml
languages:
  - name: "Language Name"
    level: "Proficiency Level"
```

## Adding New Sections

To add a new section to your resume:

1. Create a new include file in `_includes/resume/` (e.g., `awards.html`)
2. Add the corresponding data to `_data/resume.yml`
3. Include the new section in `resume.html`:

```html
{% include resume/awards.html %}
```

## Current Sections

The resume system currently includes these sections:
- **Personal Information** (`personal_info`)
- **Education** (`education`)
- **Experience** (`experience`)
- **Highlights** (`highlights`) - Notable achievements and projects
- **Skills** (`skills`)
- **Languages** (`languages`)

## Styling

All styling is contained in `_layouts/resume.html`. The styles are:
- Responsive design that works on desktop and mobile
- Print-friendly styles
- Hover effects and transitions
- Professional color scheme

## Benefits of This System

1. **Easy Content Management**: All content is in one YAML file
2. **Modular Structure**: Each section is separate and reusable
3. **Consistent Styling**: Layout and styling are centralized
4. **Version Control Friendly**: Easy to track changes in content
5. **Maintainable**: Clear separation of concerns
6. **Extensible**: Easy to add new sections or modify existing ones

## Tips

- Always test your changes by running `bundle exec jekyll serve` locally
- Use proper YAML indentation (2 spaces)
- Keep descriptions concise but informative
- Use the `post_link` fields to connect to detailed blog posts
- The system automatically handles missing optional fields gracefully
