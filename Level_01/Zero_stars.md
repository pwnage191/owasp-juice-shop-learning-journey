### Challenge
Zero Stars

### Category
Improper Input Validation

### Objective
Submit a devastating zero-star review to the store.

### Discovery Path
- Attempted to submit product feedback through the application.
- Observed that the user interface only allowed ratings between 1 and 5 stars.
- <img width="700" alt="image" src="https://github.com/user-attachments/assets/469f697e-f49b-4293-af69-517372bfebba" />
- <img width="700" alt="image" src="https://github.com/user-attachments/assets/3b0f0d22-5810-4582-9782-829b3ec9b444" />
- Suspected that the restriction was enforced only on the frontend.
- Intercepted the feedback submission request using Burp Suite.
- Modified the rating value from `1` to `0`.
- Forwarded the modified request.
- The backend accepted the rating and the challenge was solved.
- <img width="700" alt="image" src="https://github.com/user-attachments/assets/2179f989-7fd4-45a0-a52e-c36eac6c67a5" />

### Learning Drops 
- Frontend validation alone is not sufficient to enforce security controls.
- All user-supplied input should be validated on the backend.
- Attackers can bypass client-side restrictions by modifying HTTP requests.
