---
title: 'How you display an image from a fetch API response in JavaScript💻'
date: '2023-08-30'
tags: ['javascript', 'web development', 'api']
draft: false
summary: 'Use fetching API to get image data, creating HTML img element programmatically, setting its src to received API image URL, and appending to DOM for display.'
---

To do this, display an image from a fetch API response in JavaScript, you can follow these steps:

1. **Make the Fetch Request:** Use the fetch API to make a request to the server and receive the image data.
2. **Create Image Element:** Create an HTML `<img>` element programmatically using JavaScript.
3. **Set Image Source:** Set the src attribute of the `<img>` element to the URL of the image received in the API response.
4. **Append to DOM:** Append the `<img>` element to the appropriate location in the HTML DOM to display the image.

Here's an example code snippet demonstrating how to achieve this:

```javascript
// Replace 'image_url' with the actual URL of the image you want to fetch
const imageUrl = 'https://example.com/path/to/image.jpg'
// Make the fetch request
fetch(imageUrl)
  .then((response) => response.blob())
  .then((blob) => {
    // Create an image element
    const imageElement = document.createElement('img')

    // Set the src attribute to the Blob URL

    imageElement.src = URL.createObjectURL(blob)

    // Append the image element to a container in the DOM

    const imageContainer = document.getElementById('image-container')
    // Replace with your container's ID
    imageContainer.appendChild(imageElement)
  })
  .catch((error) => {
    console.error('Error fetching image:', error)
  })
```

In the example, the fetch request is made to the specified imageUrl. The response is converted to a Blob object using the `.blob()` method. Then, a new `<img>` element is created, its src attribute is set to the Blob URL, and it's appended to a container in the DOM.

You have to replace `'https://example.com/path/to/image.jpg'` with the actual URL of the image you want to fetch, and adjust the **imageContainer** variable to the ID of the HTML element where you want to display the image.

Also, you have to be aware that if you're working with images from an external domain, you might need to handle CORS (Cross-Origin Resource Sharing) issues.
