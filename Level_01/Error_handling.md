### Challenge
Error Handling

### Category
Security Misconfiguration

### Objective
Provoke an error that is neither gracefully nor consistently handled.

### Discovery Path
- Started exploring ways to trigger application errors.
- Navigated to the `/ftp` directory and attempted to access `suspicious_errors.yml`.
- Received a `403` error stating that only `.md` and `.pdf` files were allowed.
- <img width="700" alt="image" src="https://github.com/user-attachments/assets/c28be67f-edca-45bf-9c39-e37df292cd68" />
- Observed that the application was validating access based on the file extension.
- Attempted to bypass the restriction using a null byte payload:
```text
/ftp/suspicious_errors.yml%00.md
```
- <img width="700" alt="image" src="https://github.com/user-attachments/assets/8c34f6d2-c18b-4de6-b8a4-da7f38cea048" />
- The application returned a `400 Bad Request` error.
- Tried double URL encoding the null byte:

```text
/ftp/suspicious_errors.yml%2500.md
```
- <img width="700"  alt="image" src="https://github.com/user-attachments/assets/507a9a08-6689-4526-a447-a96db7ac507f" />
- The application decoded `%2500` into `%00` during processing.
- Historically, null bytes (`%00`) have been used as string terminators, causing some applications to ignore everything after the null byte.
- The double URL encoded payload bypassed the file extension restriction because the validation logic and file access logic interpreted the input differently.
- As a result, the server processed the request and disclosed the contents of the `.yml` file.
- The exposed file revealed application-specific error messages and detection rules.

### Learning Drops 
- Security controls can fail when validation and file processing logic interpret the same input differently.
- Input validation should be performed consistently across all application layers.
- Validation based solely on file extensions can be bypassed through encoding tricks.
- Key lesson: Inconsistent input handling and decoding can lead to security bypasses and information disclosure.
