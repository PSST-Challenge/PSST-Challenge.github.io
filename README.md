# PSST challenge web site
Here's the source code for https://psst.study

## Take Note!

This repository is public, so do not put any sensitive materials in here.

## Using Jekyll to Update This Web Site

With Jekyll, content is written in [Markdown](https://www.markdownguide.org/getting-started/) (like Wikipedia is), so you don't need to know any HTML to update this site. Once 

### Updating static pages
The content for static pages are in [./docs](./docs) as `*.md` files.

### Adding a blog post
The template doesn't currently list blog posts anywhere, but it wouldn't take much to make that part happen. To make a new blog post, take a look in [./docs/_posts](./docs/_posts). You can make a new file using oe of those files as a template. You'll want to follow the filename format as well.

## Setting up Jekyll for local testing

For minor edits to the content, you can probably just make the changes with GitHub's file editor. But for anything more substantial, it's a good idea to get a local Jekyll build set up. The Jekyll documentation has [complete guides](https://jekyllrb.com/docs/installation/), but here are some brief notes for people already set up and familiar with ruby/bundler/etc. 

For local testing, you'll want Jekyll installed:

```bash
gem install jekyll bundler
```

Go to the [./docs](./docs) directory and install packages
```bash
cd /path/to/this/repo/docs
bundle install
```

From there, you can build site & run a local server:
```bash
bundle exec jekyll serve
```

