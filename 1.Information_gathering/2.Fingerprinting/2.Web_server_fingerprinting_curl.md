# Web Server Fingerprinting — curl

## Objective
Identify web server behavior, security controls, caching mechanisms, supported HTTP methods, and architecture clues using the `curl` tool.

## Response Header Analysis
### Command: `curl -I http://localhost:3010`
- <img width="700" alt="image" src="https://github.com/user-attachments/assets/6593d293-5709-4a85-8dae-a28271e2f558" />
### Findings
#### Access-Control-Allow-Origin: *
- CORS header allowing cross-origin access
- Reveals cross-origin communication behavior
- Indicates API/frontend interaction support

#### X-Content-Type-Options: nosniff
- Prevents browser MIME type guessing
- Indicates security hardening is enabled
- Shows awareness of browser-based attacks

#### X-Frame-Options: SAMEORIGIN
- Prevents clickjacking attacks
- Indicates iframe restrictions are configured
- Shows browser security protections are enabled
  
#### Feature-Policy: payment 'self'
- Restricts browser payment API usage
- Reveals browser feature restrictions
- Indicates additional client-side security controls

#### X-Recruiting: /#/jobs
- Custom application header
- Reveals possible hidden route
- Indicates SPA/frontend routing behavior
- Demonstrates that custom headers may leak functionality

#### ETag
- Unique identifier for cache validation
- Reveals caching mechanisms
- May assist in framework/server fingerprinting

#### Cache-Control
- Controls resource caching behavior
- Indicates performance optimization and caching strategy

#### Last-Modified
- Timestamp of last resource modification
- Supports browser cache validation workflow

#### Vary: Accept-Encoding
- Different cache versions for different compression types
- Reveals compression-aware caching
- Indicates support for response optimization

#### Connection: keep-alive
- Keeps TCP connection open
- Indicates persistent connection support
- Improves communication efficiency

## Request and Response Inspection
### Command: `curl -v http://localhost:3010`
### Findings
#### Request Headers Sent by curl
```http
> Host: localhost:3010
> User-Agent: curl/8.19.0
> Accept: */*
```
- curl sends minimal headers by default
- Useful for observing server behavior without browser-added metadata

#### Response Headers Returned by Server
- Server intentionally exposes architecture clues
- Custom headers may reveal hidden functionality
- Response headers provide information about security and caching

## HTTP Method Enumeration
### Command: `curl -X OPTIONS http://localhost:3010 -i`
- <img width="700" alt="image" src="https://github.com/user-attachments/assets/505ea1c4-31ae-4d1a-a503-6820104dbc80" />
### Findings: `Access-Control-Allow-Methods: GET,HEAD,PUT,PATCH,POST,DELETE`
- Reveals supported HTTP methods
- Useful for understanding API capabilities
- Indicates REST-style backend behavior

### HTTP Methods
- GET: Retrieve resources
- POST: Create or submit data
- PUT: Replace existing resources
- PATCH: Partially update resources
- DELETE: Remove resources

## Learning Outcomes
- Learned basic web server fingerprinting using curl
- Observed security-related HTTP headers
- Learned how caching works using ETag and Last-Modified
- Identified custom headers revealing hidden functionality
- Enumerated supported HTTP methods using OPTIONS requests
- Improved architecture understanding through HTTP analysis
