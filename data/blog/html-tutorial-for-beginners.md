---
title: HTML Tutorial for Beginners
date: '2023-01-05'
tags: ['html', 'code', 'web development']
draft: false
summary: Example of a markdown file with code blocks and syntax highlighting
---

## What is HTML and why is it important?

HTML stands for Hypertext Markup Language, a standard markup language used to create web pages. It is essential because it is used to structure the content of a web page, and to make that content accessible to users, search engines, and web browsers. It allows developers to create web pages that can be easily read and navigated by both humans and machines. It is also an crucial tool for SEO (Search Engine Optimization), as it can help search engines understand the content of a web page and determine its relevance to particular search queries.

It consists of a series of elements that are applied to define the structure and content of a web page. These elements are represented by tags, which are written in angle brackets. Some common HTML elements include headings, paragraphs, lists, links, and images. To know better, let's deep dive into it.

## Basic Structure

An HTML document is made up of a series of elements. These elements are represented by tags, which are written in angle brackets like `<this>`. Most tags come in pairs, with an opening tag and a closing tag. The closing tag has a forward slash before the tag name like `</this>`.

Here is an example of a basic HTML structure:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My page</title>
  </head>
  <body>
    <h1>Welcome to my page!</h1>
    <p>This is where I share my thoughts and ideas.</p>
  </body>
</html>
```

### Headings

Headings are used to indicate the different sections of your page and are represented by the h1 to h6 tags. The h1 tag is the highest level heading and the h6 tag is the lowest.

```html
<h1>This is a level 1 heading</h1>
<h2>This is a level 2 heading</h2>
<h3>This is a level 3 heading</h3>
<h4>This is a level 4 heading</h4>
<h5>This is a level 5 heading</h5>
<h6>This is a level 6 heading</h6>
```

### Paragraphs

Paragraphs are used to contain blocks of text and are represented by the `p` tag.

```html
<p>This is a paragraph of text.</p>
<p>This is another paragraph of text.</p>
```

### Links

Links allow you to link to other pages or websites and are represented by the a (anchor) tag. The href attribute is used to specify the destination of the link.

```html
<a href="https://www.example.com">This is a link</a>
```

### Images

Images are used to display images on your page and are represented by the img tag. The src attribute is used to specify the source of the image. The alt attribute is used to provide an alternative text description of the image.

```html
<img src="image.jpg" alt="A description of the image" />
```

### Lists

There are two types of lists in HTML: unordered lists and ordered lists.

Unordered lists are represented by the `ul` (unordered list) tag and each list item is represented by the `li` (list item) tag.

Ordered lists are represented by the `ol` (ordered list) tag and each list item is represented by the `li` (list item) tag.

```html
<ol>
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ol>
```

### Divisions

In HTML, a division or `div` is a container element that is used to group other HTML elements together and apply styles to them. Divisions are often used to create a layout for web pages and to divide a page into sections.

Here's an example of how to use a div element in HTML:
Divisions are used to group content on your page and are represented

```html
<div>
  <p>This paragraph is inside the div element.</p>
  <p>So is this paragraph.</p>
</div>
```

It also can be applied styles to a `div` element using CSS. For example, the "style" attribute to give the `div` a background color, or a stylesheet can be used to apply more complex styles.

```html
<div style="background-color: yellow;">
  <p>This paragraph is inside a div with a yellow background.</p>
</div>
```

Divisions are very useful for creating the layout and structure of a web page, and they are an essential part of HTML.
