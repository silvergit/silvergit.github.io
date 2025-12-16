---
title: "Create Static Site With Hugo"
description: 
date: 2025-12-16T11:43:27+03:30
image: 
math: 
license: 
hidden: false
comments: true
draft: false
categories: ["learning","hugo"]
tags: ["hugo", "learning", "web", "static_site"]
---

# Introduction
As promised, I have prepared a tutorial on creating a static site using [Hugo](https://gohugo.io/) and deploying it on [GitHub Pages](https://pages.github.com/). I will update this post with every change I make to my own site and add any new features I use.

# Difference Between Static and Dynamic Sites
The first thing we need to discuss is whether you need a static site or a dynamic site. A static site is a collection of `html`, `css`, or JavaScript files that are displayed to the user exactly as they were coded. Any changes are only shown to the user by modifying the site's code. In contrast, a dynamic site displays content interactively to the user without needing to edit the code, and its content can be changed dynamically. Now, let's compare these two types of sites.

Static sites are very fast and require minimal cost for development and setup. However, their content is fixed, they have very limited features, and managing the site becomes very difficult as it grows.

Dynamic sites have dynamic content. They can interact with users, content management is very easy, and they have advanced features. However, they are slower, more complex to develop, and require significantly higher costs for setup and maintenance.

## Which One Should I Choose
If you are a blogger, need a small personal site, or want to create a small educational site, it is better to use a static site. However, if you are planning a large project, a commercial venture, or something like an online store, you should definitely opt for a dynamic site.

# Setting Up a Static Site with Hugo and GitHub Pages

## Introduction
`Hugo` is a fast and modern framework for building static sites, written in `Go`. `GitHub Pages` is a free hosting service for static sites. Combining these two provides an ideal solution for creating blogs, documentation, or personal websites.

## Advantages
- **High Speed**: Static Hugo sites load very quickly.
- **Security**: Without a database or backend code, vulnerabilities are reduced.
- **Free**: GitHub Pages provides hosting services for free.
- **Easy Management**: With Git, you can have a complete history of changes.
- **Diverse Themes**: Hundreds of free themes are available for Hugo.

## Prerequisites
1. Install `Git` ([Download](https://git-scm.com/))
2. A `GitHub` account ([Sign up](https://github.com/))
3. Install `Hugo` ([Installation Guide](https://gohugo.io/getting-started/installing/))

## Setup Steps
### 1. Install Hugo
To install Hugo, go to this [address](https://gohugo.io/installation/) and install it according to your operating system.
I use Arch Linux, so I'll install it with `pacman`:

```bash
sudo pacman -S hugo
```

### 2. Create a New Hugo Project
Now open the terminal and navigate to the directory where you want your site to be created, then run:

```bash
hugo new site your-site-name
cd your-site-name
```

That's it. You now have a static site.

### 3. Add a Theme
Go to the [Hugo Themes](https://themes.gohugo.io/) site and choose a theme for your site. Make sure to select a multilingual theme. I chose the [stack](https://github.com/CaiJimmy/hugo-theme-stack) theme.

To install `stack`, the best way is to use the ready-made template they've provided. Go to this [address](https://github.com/CaiJimmy/hugo-theme-stack-starter) and click on `Use this template`.

![create-repo-from-template](https://user-images.githubusercontent.com/5889006/156916624-20b2a784-f3a9-4718-aa5f-ce2a436b241f.png)

Now select Create new repository.

In the window that opens, in the `Repository name` field, choose the name for the new repository, which is your site. The name format should be like this:

```
username.github.io
```

where `username` is your GitHub username.

Now click `create repository`. That's it, and your site with the `stack` theme is set up on GitHub. There's just one more step: go to the settings of the created repository and select `Pages`. Now change the `Build branch` from `master` to `gh-pages`.

![change-build-branch](https://private-user-images.githubusercontent.com/16586200/298284692-12c763cd-bead-4923-b610-8788f388fcb5.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NjU5MTIzMjcsIm5iZiI6MTc2NTkxMjAyNywicGF0aCI6Ii8xNjU4NjIwMC8yOTgyODQ2OTItMTJjNzYzY2QtYmVhZC00OTIzLWI2MTAtODc4OGYzODhmY2I1LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNTEyMTYlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjUxMjE2VDE5MDcwN1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWRlMmJmYmIyM2FkZTE5OWU2NDNhNDRhNDU5ZDM5M2RmM2JiYTIzOWJmOWZkMWNkM2I4ZTY5MWRkZjk3Yjg1YWQmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.PQGXP8dMQPOwGP4NzftOSNPP8FRmZ_2z1b_2waQXWqw)

Okay, our work here is done, and we don't need to do anything else here.

### 4. Clone the Site Locally
Congratulations! You've done well so far. Let's create a clone of our site on our local system.

Open the terminal and enter this command:

```bash
git clone https://github.com/username/username.github.io.git
```

Replace `username` with your own username. For example, if you want to clone my site:

```bash
git clone https://github.com/silvergit/silvergit.github.io.git
```

Now go to the site folder:

```bash
cd silvergit.github.io
```

And run Hugo:

```bash
hugo server -D
```

The output will give you a link where you can see the local output of your site:

```bash
Built in 133 ms
Environment: "development"
Serving pages from disk
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop
```

For me, it's: `http://localhost:1313/`

### 5. First Site Post
Let's create a new page. To do this, enter this command:

```bash
hugo new content posts/hello.md
```

A new markdown file will be created for you in the `content` folder.

**Tip:** Use an editor like `vscode` for writing `markdown` files.

Copy this text into the file:

```markdown
---
title: "Hello World"
description: "First site post"
date: 2025-12-12T12:53:03+03:30
image:
math:
license:
hidden: false
comments: true
draft: false
categories: ["General"]
tags: []
---

This is my first post on this site.
```

Hugo reads the top part of the file and decides what to do with it. For example, when the file was created, what the page title is, or what tags should be introduced for this page.

The last line is what you will see in your first post. Close the file and run Hugo again.

```bash
hugo server -D
```

### 6. Configure the `config.toml` File
The configuration file is usually located at the root of the project, but sometimes you can also find it in the `config` or `config/_default` folder.

You can see a simple example of the config:

```toml
baseURL = "https://username.github.io/"
languageCode = "fa-ir"
title = "Your Site Title"
theme = "ananke"

[params]
  description = "Your site description"
```

My config looks like this:

```toml
# Change baseurl before deploy
baseurl = "https://silvergit.github.io/"
languageCode = "en-us"
title = "Morface"

# Theme i18n support
# Available values: en, fr, id, ja, ko, pt-br, zh-cn, zh-tw, es, de, nl, it, th, el, uk, ar
defaultContentLanguage = "fa"

# Set hasCJKLanguage to true if DefaultContentLanguage is in [zh-cn ja ko]
# This will make .Summary and .WordCount behave correctly for CJK languages.
hasCJKLanguage = false

# Change it to your Disqus shortname before using
disqusShortname = "hugo-theme-stack"

[pagination]
pagerSize = 5
```

All my site's config is created in separate files:

```
config
└── _default
    ├── config.toml
    ├── languages.toml
    ├── markup.toml
    ├── menu.toml
    ├── module.toml
    ├── params.toml
    ├── permalinks.toml
    └── related.toml
```

**Tip:** You can use only one file and copy all these settings into the `config.toml` file.

I use the `languages.toml` file for making the site bilingual:

```toml
[fa]
languageName = "فارسی"
languagedirection = "rtl"
title = "مورفیس"
weight = 1
[en]
languageName = "English"
languagedirection = "ltr"
title = "morface"
weight = 2
```

### 7. Upload Changes to GitHub
```bash
cd public
git init
git add .
git commit -m "First publish"
git branch -M main
git remote add origin https://github.com/username/username.github.io.git
git push -u origin main
```

## Important Notes

### Custom Domain
If you want to use a custom domain:
1. Create a `CNAME` file in the `static` folder.
2. Enter your domain name in it.
3. Configure your `DNS` according to the GitHub Pages guide.

### Search Engine Optimization
- Use SEO-Friendly themes.
- Configure meta tags correctly.
- Choose a readable URL structure.

### Persian Language Support
- Set the `languageCode` value to `fa-ir` in `config.toml`.
- Use themes with RTL support.
- Add appropriate Persian fonts.

## Useful Resources
- [Official Hugo Documentation](https://gohugo.io/documentation/)
- [GitHub Pages Guide](https://docs.github.com/pages)
- [Hugo Themes Gallery](https://themes.gohugo.io/)
- [Markdown Guide](https://www.markdownguide.org/)

## Conclusion
Using Hugo and GitHub Pages, you can set up a professional static site in the shortest time and at no cost. This method is ideal for bloggers, developers, and small businesses.