### Challenge
Exposed Metrics

### Category
Observability Failures

### Objective
Find the endpoint that serves usage data to be scraped by a popular monitoring system.

### Discovery Path
- Reviewed the challenge description for clues.
- Noticed the term "metrics", which is commonly associated with monitoring and observability systems.
- Guessed that the application might expose a metrics endpoint.
- Navigated to the `/metrics` endpoint.
- The endpoint was publicly accessible and exposed application metrics.
- <img width="700" alt="image" src="https://github.com/user-attachments/assets/055d2cc2-96cb-46c1-bd8a-c869e3d5face" />

### Learning Drops 
- Monitoring and observability endpoints can expose sensitive operational information if left publicly accessible.
- Exposed metrics may reveal application usage patterns, performance data, and internal system details.
- Information disclosed through observability features can assist attackers during reconnaissance.
**Key Lesson:** Operational and monitoring endpoints can unintentionally expose sensitive information and expand the application's attack surface.
