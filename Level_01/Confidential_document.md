### Challenge
Confidential Document

### Category
Sensitive Data Exposure

### Objective
Access a confidential document.

### Discovery Path
- Performed information gathering on the application.
- Reviewed the `robots.txt` file and discovered the `/ftp` directory.
- Browsed the exposed `/ftp` directory.
- Found the `legal.md` document and accessed it.
- <img width="800" alt="image" src="https://github.com/user-attachments/assets/d456f09e-ff66-4c32-bc80-8799ba5241ce" />

### Learning Drops 
- Files exposed through publicly accessible directories can lead to information disclosure.
- `robots.txt` may reveal hidden or sensitive application resources.
- Sensitive documents should not be stored in publicly accessible locations.
- Information gathering is often the first step toward discovering security weaknesses.
