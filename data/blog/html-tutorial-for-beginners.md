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

Headings are used to indicate the different sections of the page and are represented by the h1 to h6 tags. The h1 tag is the highest level heading and the h6 tag is the lowest.

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

Links allow us to link to other pages or websites and are represented by the a (anchor) tag. The href attribute is used to specify the destination of the link.

```html
<a href="https://www.example.com">This is a link</a>
```

### Images

To insert an image in an HTML document, it can be used the `<img>` element. The `<img>` element has a required src attribute that specifies the URL of the image. it can also be used the alt attribute to specify an alternate text for the image, which will be displayed if the image is not available.

Here's an example of how to insert an image in the HTML document:

```html
<img src="image.jpg" alt="A description of the image" />
```

To specify the size of the image, use the width and height attributes. For example:

```html
<img src="image.jpg" alt="A description of the image" width="200" height="100" />
```

To align the image within the document, use the `align` attribute. The possible values for the `align` attribute are `left`, `right`, and `middle`. For example:

```html
<img src="image.jpg" alt="A description of the image" align="left" />
```

Also use CSS to style and format images. For example, use the border property to add a border around the image, or the float property to wrap text around the image.

Here's an example of how use CSS to add a border around an image:

```css
<style>
  img {
    border: 1px solid black;
  }
</style>
<img src="image.jpg" alt="A description of the image">
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
Divisions are used to group content on the page and are represented

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

### Formatting Text

To format text on the web page, such as making it bold, italicized, or underlined. To make text bold in HTML, the `<strong>` is used or `<b>` tag. For example, to make the text "Hello, World!" bold, write:

```html
<strong>Hello, World!</strong>
```

or

```html
<b>Hello, World!</b>
```

To make text italicized in HTML, it can be used the `<em>` or `<i>` tag. For example, to make the text "Hello, World!" italicized, write:

```html
<em>Hello, World!</em>
```

or

```html
<i>Hello, World!</i>
```

To underline text in HTML, it can be used the `<u>` tag. For example, to underline the text "Hello, World!", type:

```html
<u>Hello, World!</u>
```

### Changing font size and color

To change the font size and color of text, it can used the font-size and color properties in Cascading Style Sheets (CSS). Here is an example of how to use these properties in a CSS rule to change the font size and color of an element:

```css
.example {
  font-size: 20px;
  color: blue;
}
```

To apply this style to an HTML element, give the element a class name of "example" and apply the style to the class in the stylesheet. For example:

```html
<p class="example">This text is 20px and blue.</p>
```

Also possible to use inline styles to apply these styles directly to an HTML element. For example:

```html
<p style="font-size: 20px; color: blue;">This text is 20px and blue.</p>
```

It's generally a good idea to use a stylesheet to define styles, rather than using inline styles, because it makes it easier to maintain and reuse styles throughout the website.

### Table and Forms

To create a table in HTML, use the `<table>` element. This element defines a table and is used in conjunction with `<tr>`, which defines a table row, and `<td>`, which defines a table cell. also use `<th>` elements to define table headers.

Here's an example of a simple HTML table:

```html
<table>
  <tr>
    <th>Name</th>
    <th>Age</th>
    <th>Gender</th>
  </tr>
  <tr>
    <td>John</td>
    <td>30</td>
    <td>Male</td>
  </tr>
  <tr>
    <td>Jessica</td>
    <td>25</td>
    <td>Female</td>
  </tr>
</table>
```

This would create a table with three columns (Name, Age, and Gender) and two rows of data.

To create a form in HTML, use the `<form>` element. This element is used to create an HTML form to send data to server. There are various form elements, such as <input>, <textarea>, and <select>, to create different types of form fields.

Here's an example of a simple HTML form:

```html
<form>
  <label for="name">Name:</label><br />
  <input type="text" id="name" name="name" /><br />
  <label for="email">Email:</label><br />
  <input type="text" id="email" name="email" /><br /><br />
  <input type="submit" value="Submit" />
</form>
```

This form contains two text fields (name and email) and a submit button. When the user fills out the form and clicks the submit button, the form data will be sent to the server
