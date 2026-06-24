### Challenge
Mass Dispel

### Category
Miscellaneous

### Objective
Close multiple "Challenge solved" notifications in one go.

### Discovery Path
- Started by searching for the keyword `notification` in the JavaScript files.
- Found a reference to `closeNotification(s, n.shiftKey)`.
- <img width="700" alt="image" src="https://github.com/user-attachments/assets/e4c4274a-3eea-4c22-9c22-9a3ba77b56ac" />
- The presence of `shiftKey` suggested that holding the shift key triggered special behavior.
- Reviewed the official Juice Shop documentation to better understand the notification functionality.
- Found a note stating that shift-clicking the notification close button dismisses all notifications at once.
- <img width="700" alt="image" src="https://github.com/user-attachments/assets/f9e913d6-1fa3-4326-b306-202dafe0393a" />
- Held the shift key and clicked the [x] button on a notification.
- All notifications were dismissed, completing the challenge.
- <img width="700" alt="image" src="https://github.com/user-attachments/assets/18a98a07-d2a0-4804-b26a-556aaedc7ce9" />

### Learning Drops 
- JavaScript files can reveal hidden functionality and application behavior.
- Client-side code analysis can provide clues about the application's attack surface.
- Official documentation can help uncover features that are not immediately obvious through normal usage.
- **Key Lesson:** Hidden functionality is often discoverable through client-side code and publicly available documentation.
