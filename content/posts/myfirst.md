---
title: "Hugo introduction"
subTitle : "hello word"
date: 2020-03-08T23:14:26Z
description: "this is my first page"
draft: false
author: Author Name
featured: true
label: "original"
type: posts
tags: ["tag1" , "tag2"]
categories: ["test1","test2"]
cover:
    position: left
    image: "https://photo.tuchong.com/7194943/f/1141846321.jpg"
    # can also paste direct link from external site
    # ex. https://i.ibb.co/K0HVPBd/paper-mod-profilemode.png
    alt: "<alt text>"
    caption: "<text>"
    relative: false # To use relative path for cover image, used in hugo Page-bundles
---
# Hugo Introduction

## Basic Description

Hugo is a popular open-source static site generator that allows you to create fast and efficient websites without relying on a database or server-side scripting. The structure of a Hugo site includes the following elements:

1. Content folder: This folder contains all the content of your website, including pages, blog posts, images, and other media. The content is typically written in Markdown, which is a lightweight markup language.
2. Static folder: This folder contains all the static assets of your website, including CSS stylesheets, JavaScript files, images, and other media files. These assets are not generated dynamically and are instead served as-is.
3. Archetypes folder: This folder contains templates for creating new content files. You can create templates for different types of content, such as blog posts or pages, to make it easy to create new content quickly.
4. Themes folder: This folder contains all the templates, stylesheets, and other assets for your website's theme. You can choose from a variety of pre-built themes or create your own.
5. Config file: This file contains configuration settings for your Hugo site, such as the site title, language, and other global settings.
6. Layouts folder: This folder contains templates for generating the HTML output of your website. You can create templates for different types of pages, such as the homepage, blog index, or individual blog posts.
7. Data folder: This folder contains data files that are used to generate your website, such as site configuration settings, lists of authors or categories, or other metadata.

<img src="https://i.328888.xyz/2023/03/15/JZSfx.png" alt="JZSfx.png" style="zoom:50%;text-align: center;" />

**In this case, we need to introduce our theme in theme folder, in terms of structure of theme, logically it the same as the default one.**

It's worth to notice that Config file [config.toml] we define a lot of global variables, I will reveal in the next section, including how to introduce custom theme.

## Hugo Theme

Hugo themes are collections of templates, stylesheets, and other assets that determine the appearance and behavior of a Hugo website. The structure of a Hugo theme typically includes the following elements:

1. Layouts folder: This folder contains the templates that generate the HTML output of your website. It is organized by the content type (e.g., posts, pages) and can include a variety of template files, such as base templates, list templates, and single templates.
2. Static folder: This folder contains all the static assets of the theme, including CSS stylesheets, JavaScript files, images, and other media files. These assets are not generated dynamically and are instead served as-is.
3. Assets folder: This folder contains the source files for the theme's stylesheets and scripts, as well as any other assets that need to be compiled or processed before being served to the browser.
4. Config file: This file contains configuration settings for the theme, such as the theme name, author, and other global settings.
5. Archetypes folder: This folder contains templates for creating new content files using the theme.
6. i18n folder: This folder contains translation files for the theme in different languages.
7. Shortcodes folder: This folder contains reusable snippets of code that can be used in content files to add custom functionality to the website.
8. Partials folder: This folder contains smaller, reusable template files that can be included in other templates to reduce duplication and improve maintainability.

By following this structure, Hugo themes can be easily shared and reused, allowing developers to quickly create new websites with a consistent look and feel.

### Config.toml file

In config.toml, we can setup theme and define all the global variables, such as website url, website name, your name as the author, social media and so on.

#### Introduce theme


{{< highlight Toml "linenos=table" >}}
theme = 'dark-theme'  # the name should match your theme's name in the theme folder
{{< /highlight >}}


#### Setup menu
{{< highlight Toml "linenos=table" >}}
# setup menu
sectionPagesMenu = "main"
[menu]
  [[menu.main]]
    name = "Home"
    pre = "home"
    url = "/"
    weight = 1
  [[menu.main]]
    name = "My Project"
    pre = "posts"
    url = "/posts/"
    identifier = "posts"
    weight = 2
  [[menu.main]]
    name = "Tags"
    pre = "tag"
    identifier = "tags"
    url = "/tags/"
    weight = 3
  [[menu.main]]
    name = "Abouts"
    pre = "about"
    identifier = "about"
    url = "/about/"
    weight = 4
{{< /highlight >}}


About page is not the default page, 