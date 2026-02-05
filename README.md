# Clement Wang's personal website

Personal blog and portfolio, built with [Jekyll](https://jekyllrb.com/) and the [Hux Blog](https://github.com/Huxpro/huxpro.github.io) theme.

### Local development

1. Install [Ruby](https://www.ruby-lang.org/) and [Bundler](https://bundler.io/), then:

   ```sh
   bundle install
   ```

2. Serve the site (default: <http://localhost:4000>):

   ```sh
   bundle exec jekyll serve
   # or: npm start
   ```

### Theme customization

Theme source lives in `_includes/`, `_layouts/`, and `less/`. To rebuild CSS after editing `.less` files, use [Grunt](https://gruntjs.com/) (see `Gruntfile.js`).

More details: [_doc/Manual.md](_doc/Manual.md) (theme manual).

---

**License.** Apache 2.0. This site uses the [Hux Blog](https://github.com/Huxpro/huxpro.github.io) theme (Copyright (c) 2015-present Huxpro), derived from [Clean Blog Jekyll Theme](https://github.com/BlackrockDigital/startbootstrap-clean-blog-jekyll/) (MIT).
