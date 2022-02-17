# PSST challenge web site
Here's the source code for https://psst.study

## Take Note!
This is open source, so sensitive data and information must not go in this repo.

## Getting Jekyll set up
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

# Adding a blog post
Take a look in [./docs/_posts](./docs/_posts). You can make a new file using another post as a template, following the 
filename format as well.

# Updating static pages
The content for static pages are in [./docs](./docs) as `*.markdown` files. 