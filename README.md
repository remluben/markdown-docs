# Remluben Markdown Docs

## Description

Simple satic HTML page for the visualization of markdown files.

When the *docs* directory is called after the installation, the *index.html* file automatically loads the *index.md* file.

Additional Markdown files stored under *docs/pages* can easily be linked with e.g. */pages/changelog.md*.

Since the URL is updated with the URL parameter *?page=pages/xyz.md* for every internal link on the page, every page can be called up directly as required.

### Why?

This small HTML file is supposed to create a simple possibility to show documentation from several markdown files in an online version for browsers directly via the URL of web applications.

## Installation

1. Checkout this repository
1. Copy the contents of *docs* into an accessible directory of your target web application to be documented
1. Navigate to e.g. [https://www.your-applications-domain.xy/subdirectory/docs](https://www.your-applications-domain.xy/subdirectory/docs)

### Information on the example structure

By default, *docs* contains

* an *index.md* file, which is intended for general documentation or the linking of further pages
* various example *pages*
 * *changelog.md* for the creation of a change history
 * *api.md* for documenting APIs in use or provided by the application itself
 * *development.md* for documenting development stuff

Further information on the areas is available directly in the individual markdown documents.

### Run the documentation without a web server in the local environment

If you want to create documentation without a web server available in the local environment, use the web server available in PHP:

```
cd /path/to/docs/base/directory/
php -S localhost: 8000
# Open http://localhost:8000/docs in your browser to see the example index
```

## Howto

### Link a markdown page correctly

To link a page in markdown (see sample documents) a link must begin with */*.

Example: `[Changelog](/pages/changelog.md)`

### Change the logo

By default, the logo of [Remluben](https://www.remluben.at) from an URL ​​is displayed in the header area.

If you want to adjust the header area, you have to adjust the `<script>` tag with id `#app-header` in *index.html*. Use any HTML.

### Change the footer

By default, the copyright notice for [Remluben](https://www.remluben.at) is displayed in the footer area.

If you want to adjust the footer area, you have to adjust the `<script>` tag with id `#app-footer` in *index.html*. Use any HTML.

## Technology - how does this website work?

* [Github-Markdown-CSS](https://github.com/sindresorhus/github-markdown-css) to enable HTML formatting based on Github for the markdown-based pages
* [Showdown](https://github.com/showdownjs/showdown) JavaScript library for rendering the markdown files as HTML.

Markdown files are loaded via AJAX and inserted directly into the page.

### What happens if the links are broken?

If broken links to documents, that are not available, are used, *index.md* is automatically displayed.

If *index.md* cannot be loaded, no content can be displayed. You only see a blue background and an empty content area on a white background.

## Versions

### 1.0.0 (210501)

Basic version

## Developers

&copy; [Remluben](https://www.remluben.at)

Benjamin Ulmer, ulmer.benjamin@gmail.com 