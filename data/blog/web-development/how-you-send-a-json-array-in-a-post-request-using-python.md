---
title: 'How you send a JSON array in a post request using Python 🐍 💻'
date: '2023-08-27'
tags: ['json', 'web development', 'python']
draft: false
summary: 'It starts by creating a valid JSON array then ensuring proper headers, including its content type followed by converting the array to a string using Python and fetching with javaScript'
---

Here is the way you do that

### Steps to follow! 🌟

1. **Create the JSON Array**: First, you need to create the JSON array that you want to send in your POST request. Make sure the data is properly formatted as a valid JSON array.
2. **Set Headers:** In your POST request, you'll need to set the appropriate headers, including the "Content-Type" header to indicate that you're sending JSON data. Commonly used content types for JSON are "application/json" or "application/json;charset=utf-8".
3. **Convert to String:** Convert your JSON array to a string format. Most programming languages have built-in functions to do this. For example, in Python, you can use the json.dumps() function.
4. **Send POST Request:** Use a library or framework to send the POST request. Examples of popular libraries include requests in Python, fetch in JavaScript, or built-in libraries like HttpURLConnection in Java.

Assuming you are going to use Python

```python
import requests
import json

# Your JSON array
data = [1, 2, 3, 4, 5]

# Convert JSON array to a string
json_data = json.dumps(data)

# Set the headers
headers = {
    'Content-Type': 'application/json'
}

# Send POST request
response = requests.post('https://example.com/api/endpoint', data=json_data, headers=headers)

# Check the response
if response.status_code == 200:
    print("POST request successful!")
else:
    print("POST request failed.")
```

Please replace 'https://example.com/api/endpoint' with the actual URL of the API endpoint you are sending the POST request to.

On the frontend, you are going to use the `fetch` API:

```javascript
const data = [1, 2, 3, 4, 5]

fetch('https://example.com/api/endpoint', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
  },
  body: JSON.stringify(data),
})
  .then((response) => {
    if (response.ok) {
      console.log('POST request successful!')
    } else {
      console.log('POST request failed.')
    }
  })
  .catch((error) => {
    console.error('An error occurred:', error)
  })
```

That’s the simplest way to simulate sending a JSON array in a post request. Hope it helps
