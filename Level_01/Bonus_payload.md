### Challenge
Bonus Payload

### Category
XSS

### Objective
Use the bonus payload in the DOM XSS challenge.

### Discovery Path
- Explored the web application and identified the search functionality.
- Observed that the search query was reflected back into the page.
- Tested HTML injection using `<b>Hello</b>` and confirmed that user input was rendered as HTML.
- Inspected the DOM and found that user input was inserted without proper sanitization.
- Injected the provided SoundCloud `<iframe>` payload into the search parameter.
- The payload was successfully rendered, completing the challenge.
- <img width="700" alt="image" src="https://github.com/user-attachments/assets/7fe31e3c-e1d9-40c4-8a5b-997d96f4c0f7" />

### Learning Drops 
- User input should be sanitized before being inserted into the DOM.
- Applications should validate and restrict embedded content from untrusted sources.
- Rendering user-controlled HTML can lead to XSS and content injection vulnerabilities.
