### Challenge
DOM XSS

### Category
Cross-Site Scripting (XSS)

### Objective
Perform a DOM-based XSS attack using:
```html
<iframe src="javascript:alert(`xss`)">
```

### Discovery Path
- Explored the web application and identified the search functionality.
- Observed that the search query was reflected back to the page.
- Tested HTML injection using `<b>Hello</b>` and confirmed that the input was rendered as HTML.
- Inspected the page using Developer Tools and noticed that user input was inserted into the DOM without proper sanitization.
- <img width="700"  alt="image" src="https://github.com/user-attachments/assets/091f65a6-85e6-4097-a9ea-7a69ed505ba6" />
- Injected the XSS payload using an `<iframe>` element with a `javascript:` URL.
- Successfully triggered a JavaScript alert and solved the challenge.
- <img width="700"  alt="image" src="https://github.com/user-attachments/assets/26770700-8fd9-42ae-9c4a-6629d8500cba" />

### Learning Drops 
- User input should be sanitized before being inserted into the DOM.
- Dangerous URL schemes such as `javascript:` should be restricted or validated.
- DOM-based XSS occurs entirely within the browser when client-side JavaScript processes untrusted input.
