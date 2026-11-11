# Attack Surface Map

Illustrative architecture. Solid = observed; dashed = expected, unconfirmed. Replace with real observations.

```mermaid
flowchart TD
  U[User Browser<br/>Firefox ESR proxied] --> P[Intercepting proxy<br/>Burp 127.0.0.1:8080 / ZAP localhost:8081]
  P --> W[Web server / application gateway<br/>HTTP and HTTPS TLS]
  W --> A[Public pages<br/>Home, About, Contact]
  W --> B[Authentication<br/>Login, Register]
  W --> C[Application functions<br/>Search, Forms]
  W --> D[Authorized user area<br/>Dashboard, Profile]
  A -.-> E[Backend components - not confirmed<br/>APIs, application logic, database]
  B -.-> E
  C -.-> E
  D -.-> E
  style E stroke-dasharray: 5 5
```

## Observed external dependencies (practice site)

| Category | Observation |
|---|---|
| Web server | gws |
| Protocol | HTTP/2 over TLS; alt-svc advertises HTTP/3 |
| Redirect | google.com -> https://www.google.com/ (301) |
| Cookies | AEC, NID, __Secure-STRP |
| Third-party hosts | www.gstatic.com, fonts.gstatic.com, csp.withgoogle.com |
| Browser-side security | Report-only CSP, X-Frame-Options SAMEORIGIN |
