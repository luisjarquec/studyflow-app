# StudyFlow Website

This directory contains the source code for the StudyFlow project website, built with Jekyll.

## Running Locally

1. Install Jekyll and Bundler:
   ```bash
   gem install jekyll bundler
   ```

2. Install dependencies:
   ```bash
   bundle install
   ```

3. Serve the site:
   ```bash
   bundle exec jekyll serve
   ```

## Deployment

To deploy to GitHub Pages:

1. Go to your repository settings on GitHub.
2. Navigate to the "Pages" section.
3. Choose the source as "GitHub Actions" (recommended for custom builds) or configure a workflow to build from this `website` directory.

Alternatively, if you want to use the default Source options (Root or Docs), you might need to move these files to the root or `docs` folder (but `docs` is used by Sphinx).

Recommended: Use a GitHub Action to build and deploy this folder to the `gh-pages` branch.
