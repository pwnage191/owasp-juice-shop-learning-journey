### Challenge
Missing encoding

### Category
Improper input validation

### Objective
Retrieve the photo of Bjoern's cat in "melee combat-mode".

### Discovery Path
- Started by researching references to Bjoern's cat and found that the cat's name is Zaya.
- Explored the application and navigated through the available pages.
- Observed a broken image in the Photo Wall.
- Inspected the image URL and noticed the presence of the `#` character.
- The `#` character is a special URL fragment delimiter. Everything after it is processed by the browser and is not sent to the server as part of the request.
- When a filename or path contains `#`, it must be URL-encoded as `%23`; otherwise, the browser treats it as a fragment identifier instead of part
  of the resource name.
- URL-encoded the `#` character and reloaded the image.
- The image loaded successfully, revealing the photo and completing the challenge.
- <img width="700" alt="image" src="https://github.com/user-attachments/assets/79b92eea-b3c1-4694-852e-158585a390bd" />

### Learning Drops 
- Understanding the root cause of an issue is often more valuable than trying random fixes.
- Special characters in URLs can have specific meanings that affect how requests are processed.
- Broken functionality can sometimes be caused by incorrect handling of special characters rather than missing resources.
- **Key Lesson:** Incorrect handling of special URL characters can prevent applications from accessing resources as intended.
