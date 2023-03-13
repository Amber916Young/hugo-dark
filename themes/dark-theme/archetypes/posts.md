---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
description: "this is description"
draft: false
featured: true
label: "orginal"
author: {{ .Site.Params.author}}
lastmod: {{ .Date }}
tags: [tag1, tag2, tag3]
categories: [cate1,cate2]
cover:
    position: <left,right>
    image: ""
    alt: "<alt text>"
    caption: "<text>"
---

