API Security Assessment Report

**Author:** Kimberly Farai Mago  
**Programme:** Future Interns — Cybersecurity Track  
**API Tested:** [JSONPlaceholder](https://jsonplaceholder.typicode.com)  
**Assessment Type:** Read-Only Security Risk Analysis  

Project Overview

This project presents a professional API security assessment conducted on JSONPlaceholder — a public REST API used for testing and prototyping. The goal was to simulate the type of security audit performed by AppSec consultants and cybersecurity agencies on SaaS platforms and production APIs.

The assessment identifies real-world vulnerabilities that would be critical if this API were deployed in a live environment, and provides actionable remediation recommendations for each finding.

> **Ethical Disclaimer:** This assessment was conducted exclusively on a demo API designed for public testing. No exploitation, data manipulation, or denial-of-service testing was performed. All requests were read-only (GET). This project is for educational purposes only.


Tools Used

| Tool | Purpose |
|------|---------|
| Postman | Sending HTTP requests and analysing API responses |
| Browser DevTools | Inspecting network traffic, headers, and response data |


Scope

**Endpoints Tested:**
- `/users`
- `/posts`
- `/comments`

**In Scope:**
- Unauthenticated endpoint access
- Response data analysis
- HTTP header inspection
- Authorization and access control review

**Out of Scope:**
- Exploitation or bypass attempts
- POST/PUT/DELETE abuse
- Private or production APIs
- Load/stress testing


Methodology

1. Sent GET requests to each endpoint without any authentication or API key
2. Observed and documented all response data
3. Inspected HTTP request and response headers via DevTools
4. Evaluated access control across different user records
5. Assessed risk level for each finding using a High / Medium / Low scale
6. Mapped findings against the [OWASP API Security Top 10](https://github.com/OWASP/API-Security)


Findings Summary

| # | Finding | Endpoint | Risk Level |
|---|---------|----------|------------|
| 1 | Unauthenticated Access to Sensitive User Data | `/users` | 🔴 HIGH |
| 2 | Exposure of Email Addresses | `/comments` | 🔴 HIGH |
| 3 | Lack of Access Control | `/posts` | 🔴 HIGH |
| 4 | Excessive Data Exposure | `/users` | 🟡 MEDIUM |
| 5 | Lack of Pagination | `/comments`, `/posts` | 🟡 MEDIUM |
| 6 | Broken Object-Level Authorization (BOLA) | `/comments` | 🔴 HIGH |
| 7 | Predictable Resource IDs | `/comments` | 🟡 MEDIUM |
