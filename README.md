# jekyll

Certainly! Here's a `README.md` that outlines the steps for setting up Jekyll for a GitHub Pages site on an Ubuntu system. This document is designed to guide users through the entire process, from setting up the environment to pushing the site live on GitHub Pages.

```markdown
# Setting Up Jekyll for a GitHub Pages Site on Ubuntu

This guide walks you through the process of setting up a Jekyll-based static site on Ubuntu, and then publishing it to GitHub Pages.

## Prerequisites

- A GitHub account (if you don't have one, create it at [github.com](https://github.com))
- Ubuntu (or any other Debian-based Linux distribution)
- Basic knowledge of using the command line

## Step 1: Install Required Software

### 1.1 Update your package list

Before installing anything, update your package list to ensure you're getting the latest versions available in the Ubuntu repositories.

```bash
sudo apt update
```

### 1.2 Install Ruby and dependencies

Jekyll is a Ruby-based static site generator, so you'll need to install Ruby along with some essential dependencies.

```bash
sudo apt install ruby-full build-essential zlib1g-dev
```

### 1.3 Configure Ruby environment

By default, Ubuntu installs Ruby globally. To avoid using `sudo` when installing Ruby gems, configure your system to install gems in your user directory:

```bash
echo '# Install Ruby Gems to ~/.gem' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/.gem"' >> ~/.bashrc
echo 'export PATH="$HOME/.gem/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

### 1.4 Install Bundler and Jekyll

Bundler is a dependency manager for Ruby, and Jekyll is the static site generator that we will use. Install both by running:

```bash
gem install bundler jekyll
```

## Step 2: Create a New Jekyll Site

### 2.1 Generate a new Jekyll site

Once Ruby and Jekyll are installed, create a new Jekyll site by running the following command:

```bash
jekyll new my-site
```

Replace `my-site` with the name of your project. This will create a new directory with the necessary structure for a Jekyll site.

### 2.2 Navigate into the site directory

Move into the newly created directory:

```bash
cd my-site
```

### 2.3 Install the required dependencies

In the Jekyll site directory, there is a `Gemfile` that lists all the required Ruby gems (including Jekyll itself). Install these dependencies by running:

```bash
bundle install
```

This will install the required gems and make sure your site is ready for local development.

### 2.4 Serve the site locally

To preview your site locally, start the Jekyll development server:

```bash
bundle exec jekyll serve
```

By default, the site will be available at `http://localhost:4000`.

Open a web browser and visit `http://localhost:4000` to see your site in action!

## Step 3: Create a GitHub Repository

### 3.1 Create a new repository on GitHub

1. Log in to your GitHub account and go to the [GitHub homepage](https://github.com).
2. Click the **+** icon in the top right corner and select **New repository**.
3. Name the repository `username.github.io`, replacing `username` with your GitHub username (e.g., if your GitHub username is `john`, the repository should be named `john.github.io`).
4. Choose **Public** for visibility (unless you want it private, but you'll need a GitHub Pro account for that).
5. Click **Create repository**.

### 3.2 Initialize a Git repository in your Jekyll project

If your Jekyll site isn't already initialized as a Git repository, run the following commands in your Jekyll site directory:

```bash
git init
```

### 3.3 Add your GitHub repository as a remote

Replace `username` with your GitHub username in the following command:

```bash
git remote add origin https://github.com/username/username.github.io.git
```

### 3.4 Add and commit the changes

Now that your site is initialized as a Git repository, add all files to the staging area:

```bash
git add .
```

Commit the changes:

```bash
git commit -m "Initial commit with Jekyll site"
```

### 3.5 Push the site to GitHub

Push your local repository to GitHub using:

```bash
git push -u origin master
```

After a few moments, your site should be live at `https://username.github.io`.

## Step 4: Customize Your Jekyll Site

You can now customize your Jekyll site to fit your needs.

### 4.1 Edit the `_config.yml` file

The `_config.yml` file contains global settings for your site. You can change the title, description, URL, and more. Here's an example of what the file might look like:

```yaml
title: My Jekyll Site
description: A simple blog powered by Jekyll and GitHub Pages
author: Virachai Wongsena
theme: minima

url: "https://virachai.github.io/jekyll"
baseurl: ""  # This is important for GitHub Pages
```

### 4.2 Add new pages

You can add new pages to your Jekyll site by creating new `.md` or `.html` files. For example, create an `about.md` file:

```bash
touch about.md
```

Add your content in Markdown format.

### 4.3 Add new posts

To add a new blog post, create a new file in the `_posts` directory. The file should be named using the following format: `YEAR-MONTH-DAY-title.md` (e.g., `2024-12-25-my-first-post.md`).

Here’s an example of a basic post:

```markdown
---
layout: post
title: "Welcome to My Blog"
date: 2024-12-25
categories: jekyll update
---

This is my first post on my new Jekyll-powered blog. I’m excited to start writing!
```

### 4.4 Customize the theme

Jekyll comes with several built-in themes, but you can also customize or add your own styles. To change the theme, simply edit the `_config.yml` file and specify a theme (e.g., `minima`):

```yaml
theme: minima
```

You can also customize the layout by editing files in the `_layouts` folder or by adding your own CSS in `assets/css`.

## Step 5: Push Changes to GitHub

Whenever you make changes to your site (e.g., adding pages, modifying content, etc.), follow these steps to push them to GitHub:

### 5.1 Stage and commit changes

```bash
git add .
git commit -m "Update content"
```

### 5.2 Push changes

```bash
git push
```

GitHub Pages will automatically rebuild your site with the changes you pushed, and it will be live shortly after.

## Step 6: Configure GitHub Pages (Optional)

If your repository is named `username.github.io`, GitHub will automatically recognize it as a GitHub Pages site and serve the content.

If you need to configure GitHub Pages for a different repository, follow these steps:

1. Go to your GitHub repository.
2. Navigate to the **Settings** tab.
3. Scroll down to the **Pages** section.
4. Under **Source**, select the `main` (or `master`) branch and `/ (root)` for the folder.

GitHub Pages will then build and serve your site from the specified branch.

## Conclusion

You've successfully set up a Jekyll-powered site on GitHub Pages using Ubuntu! You can continue customizing your site, adding content, and using GitHub for version control. Whether you're creating a blog, portfolio, or documentation site, Jekyll and GitHub Pages offer a simple and powerful solution.