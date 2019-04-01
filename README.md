# wintersmith-search

![npm](https://img.shields.io/npm/v/wintersmith-search.svg)
![npm](https://img.shields.io/npm/dt/wintersmith-search.svg)

A plugin to generate a search.json to be used with [Simple-Jekyll-Search](https://github.com/christian-fei/Simple-Jekyll-Search).

Requires wintersmith-contents

```bash
npm install wintersmith-contents --save
npm install wintersmith-search --save
```

```JSON
  "plugins": [
    "wintersmith-contents",
    "wintersmith-search"
  ]
```

sample search page

```pug
extends layout

block append head
    script(src="https://unpkg.com/simple-jekyll-search@1.5.0/dest/simple-jekyll-search.min.js")
    script.
        document.addEventListener("DOMContentLoaded", function () {
        var sjs = SimpleJekyllSearch({
        searchInput: document.getElementById('searchInput'),
        resultsContainer: document.getElementById('resultsContainer'),
        json: '/search.json'
        });
        document.getElementById('searchInput').focus();
        });

block content
    .search
        h1 search
        input#searchInput(type='text', placeholder='Search blog posts..')
        ul#resultsContainer

```