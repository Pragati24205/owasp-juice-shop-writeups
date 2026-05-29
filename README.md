# OWASP Juice Shop Writeups

This repository documents my work on OWASP Juice Shop, a deliberately vulnerable web application used for security training and practice. I worked through these challenges as part of building my offensive security skills, focusing on understanding the root cause of each vulnerability rather than just popping the alert.

Each writeup covers my methodology, what I found, why it works, and what the real-world impact would be. Some challenges I went beyond the intended solve and testing edge cases, replaying requests with different tokens, or chaining findings together.

## Challenges

| # | Challenge | Category | Severity |
|---|-----------|----------|----------|
| 01 | [Find Scoreboard](./writeups/01-scoreboard.md) | Miscellaneous | Low |
| 02 | [DOM XSS](./02-dom-xss.md) | XSS | High |
| 03 | [Bonus Payload](./03-bonus-payload.md) | XSS | High |
| 04 | [Reflected XSS](./04-reflected-xss.md) | XSS | High |
| 05 | [Error Handling](./05-error-handling.md) | Security Misconfiguration | Medium |
| 06 | [Login Admin](./06-login-admin.md) | Injection | Critical |
| 07 | [Admin Section](./07-admin-section.md) | Broken Access Control | High |
| 08 | [Five-Star Feedback](./08-five-star-feedback.md) | Broken Access Control | Medium |
| 09 | [Zero Stars](./09-zero-stars.md) | Improper Input Validation | Low |
| 10 | [View Basket](./10-view-basket.md) | Broken Access Control | High |
| 11 | [Forged Feedback](./11-forged-feedback.md) | Broken Access Control | Medium |
| 12 | [Admin Registration](./12-admin-registration.md) | Improper Input Validation | Critical |
| 13 | [API-based XSS](./13-api-xss.md) | XSS | Critical |
| 14 | [Forged Review](./14-forged-review.md) | Broken Access Control | Medium |
| 15 | [Login Bender](./15-login-bender.md) | Injection | Critical |
| 16 | [Password Strength](./16-password-strength.md) | Broken Authentication | High |
| 17 | [User Credentials](./17-user-credentials.md) | Injection | Critical |
| 18 | [Web3 Sandbox](./18-web3-sandbox.md) | Broken Access Control | Medium |
| 19 | [Bjoern's Favorite Pet](./19-bjoerns-pet.md) | Broken Authentication | High |
| 20 | [GDPR Data Erasure](./20-gdpr-erasure.md) | Broken Authentication | High |
| 21 | [Reset Jim's Password](./21-reset-jims-password.md) | Broken Authentication | High |
| 22 | [Manipulate Basket](./22-manipulate-basket.md) | Broken Access Control | High |
| 23 | [Product Tampering](./23-product-tampering.md) | Broken Access Control | Medium |
| 24 | [CSRF](./24-csrf.md) | CSRF | Medium |
| 25 | [Login Jim](./25-login-jim.md) | Injection | Critical |
| 26 | [Database Schema](./26-database-schema.md) | Injection | High |
| 27 | [Client-side XSS Protection](./27-client-side-xss.md) | XSS | Critical |
