
title: "Complete Hugo Tutorial for Beginners"
date: 2024-01-20
draft: false
description: "Step by step guide to install and use Hugo"
categories: ["Tutorial", "Web Development"]
tags: ["hugo", "tutorial", "web development"]

Hugo Tutorial from Zero to Hero 📚
In this complete tutorial, we'll learn Hugo from scratch.

Chapter 1: Installing Hugo
On Linux
bash
# Method 1: Snap
sudo snap install hugo --channel=extended

# Method 2: Manual
wget https://github.com/gohugoio/hugo/releases/download/v0.125.5/hugo_extended_0.125.5_linux-amd64.tar.gz
tar -xvzf hugo_extended_0.125.5_linux-amd64.tar.gz
sudo mv hugo /usr/local/bin/
On Windows
powershell
choco install hugo-extended
On macOS
bash
brew install hugo
Chapter 2: Creating First Site
bash
# Create new project
hugo new site mysite
cd mysite

# Add theme
git init
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke

# Configuration
echo 'theme = "ananke"' >> hugo.toml

# Run server
hugo server -D
Chapter 3: Project Structure
text
mysite/
├── archetypes/       # Content templates
├── content/          # Site content
├── layouts/          # HTML templates
├── static/           # Static files
├── themes/           # Themes
└── hugo.toml         # Configuration file
Chapter 4: Creating Content
Create Page
bash
hugo new about.md
Create Blog Post
bash
hugo new posts/my-first-post.md
Chapter 5: Advanced Configuration
Multilingual
toml
[languages]
  [languages.fa]
    languageName = "فارسی"
    weight = 1
    
  [languages.en]
    languageName = "English"
    weight = 2
Menu
toml
[[menu.main]]
  name = "Home"
  url = "/"
  weight = 1
Chapter 6: Deployment
GitHub Pages
bash
# Build site
hugo

# Upload to GitHub
cd public
git init
git add .
git commit -m "Deploy site"
git branch -M main
git remote add origin https://github.com/username/repo.git
git push -u origin main
Conclusion
Hugo is a powerful tool worth learning.

Level: Beginner
Reading Time: 20 minutes
Prerequisites: Basic terminal knowledge
