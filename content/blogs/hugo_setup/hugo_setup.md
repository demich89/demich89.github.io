---
title: "Using Hugo with GitHub Pages"
date: 2025-11-29
draft: false
github_link: "https://github.com/gurusabarish/hugo-profile"
author: "Michel"
tags:
  - Hugo
  - GitHub Pages
  - Portfolio
  - Web Development
image: /images/hugo-logo-wide.svg
description: ""
toc: 
---

This document describes how to build and deploy a Hugo-based personal profile or résumé website using GitHub Pages.

## 1. Install and Initialize Hugo

```
# Install Hugo on macOS via Homebrew
brew install hugo          
# Create a project directory for the site
mkdir website_example      
# Navigate into the project folder
cd website_example         
# Initialize a new Hugo site (use --force only if the folder isn’t empty)
hugo new site .            
```

## 2. Add hugo Profile
[Hugo-profile](https://themes.gohugo.io/themes/hugo-profile/)

```
# Initialize a new local Git repository
git init
# Add the Hugo Profile theme as a Git submodule
git submodule add https://github.com/gurusabarish/hugo-profile.git themes/hugo-profile
# Copy static assets from the theme’s example site
rsync -av themes/hugo-profile/exampleSite/static/ ./static/
# Copy example content into your project
rsync -av themes/hugo-profile/exampleSite/content/ ./content/
# Copy hugo.yaml to root directorz
cp themes/hugo-profile/exampleSite/hugo.yaml .
# Delete the default Hugo configuration file
rm hugo.toml        
```

## 3. Start Hugo local
```
# --disableFastRender      # force full rebuilds to reflect all changes immediately
# --noHTTPCache            # disable browser caching during development
# --cleanDestinationDir    # clean the /public directory before rebuilding
hugo server --disableFastRender --noHTTPCache --cleanDestinationDir
```

## 4. Setup github
Make sure to set you repo to public

![github_example](/blogs/hugo_setup/website_example.png)

From pages select GitHub Actions and select at the hugo tile Hugo configure

![pages_gitaction](/blogs/hugo_setup/pages_gitaction.png)

Commit the changes from the hugo.yml workflow.

![commit_hugo](/blogs/hugo_setup/commit_hugo.png)


