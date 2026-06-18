## Endpoint discovery

### Objective
Discover additional directories and endpoints exposed by OWASP Juice Shop.

### Discovery Path
1. Started directory enumeration using Gobuster.
2. Observed that Juice Shop (SPA) returned the same `200 OK` response for invalid routes.
3. Excluded the common response length (`9903`) to reduce false positives.
4. Re-ran Gobuster and identified interesting endpoints.
<img width="600" alt="image" src="https://github.com/user-attachments/assets/e28b10e4-49e5-46ca-b99a-a7e317239f37" />
<img width="600" alt="image" src="https://github.com/user-attachments/assets/613b4e77-2671-498c-b156-20c8a7f185f1" />
5. A 500 response during enumeration is not necessarily a dead end. It often indicates that the route exists but requires specific parameters,
   authentication, or a deeper path.

### Learning drops
- SPAs may return the same 200 OK response for valid and invalid routes.
- Response-length filtering helps reduce false positives during enumeration.
- Endpoint discovery helps map the application's attack surface.
