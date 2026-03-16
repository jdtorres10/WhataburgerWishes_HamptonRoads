# Security Policy

## Project Scope

This is a static geospatial research project consisting of a client-side HTML/JavaScript
interactive map. It contains no backend, no database, no authentication system, and no
user data collection at this time.

---

## Supported Versions

| Version | Supported |
|---------|-----------|
| Latest (`main` branch) | ✅ Yes |
| All prior commits | ❌ No — please verify against latest |

---

## Reporting a Vulnerability

If you discover a security vulnerability in this project, **please do not open a public
GitHub issue.** Public disclosure before a fix is in place puts other users of this code
at risk.

Instead, please report it privately using one of the following methods:

**GitHub Private Advisory (preferred)**
Navigate to the Security tab of this repository and click
`Report a vulnerability` to open a private advisory draft.
This keeps the disclosure confidential until resolved.

**Email**
If you are unable to use GitHub's advisory system, you may email the maintainer
directly. Please include:
- A clear description of the vulnerability
- Steps to reproduce or a proof-of-concept
- The potential impact in your assessment
- Your preferred contact method for follow-up

---

## What to Report

Even though this is a static project, the following are in scope and worth reporting:

- **Exposed credentials or API keys** accidentally committed to the repository
- **Malicious dependency** introduced via CDN links (Leaflet, CartoDB, Google Fonts)
- **Cross-site scripting (XSS)** vulnerabilities in any dynamic content or future form fields
- **Sensitive personal data** unintentionally included in any data files or commits
- **Typosquatting or dependency confusion** if external packages are added in future

The following are out of scope for this project at its current stage:

- Vulnerabilities in third-party services (CartoDB, OpenStreetMap, Google Fonts CDN)
- Issues that require physical access to a device
- Social engineering attacks

---

## Response Timeline

| Stage | Target timeframe |
|-------|-----------------|
| Acknowledgement of report | Within 72 hours |
| Initial assessment | Within 7 days |
| Fix or mitigation published | Within 30 days for critical issues |
| Public disclosure | Coordinated with reporter after fix |

---

## Security Best Practices for Contributors

If you fork or contribute to this project, please follow these practices:

**Never commit credentials.** API keys, tokens, passwords, and private URLs must never
be placed in any file tracked by Git — including `index.html`, JavaScript files, or
configuration files. Use GitHub Secrets and environment variables instead.

**Audit CDN dependencies.** All external scripts are loaded from
`cdnjs.cloudflare.com`, `unpkg.com`, and `fonts.googleapis.com`. If you add a new
CDN dependency, verify the integrity hash using Subresource Integrity (SRI) attributes:

```html
<script
  src="https://example.com/library.js"
  integrity="sha384-[hash]"
  crossorigin="anonymous">
</script>
```

**Sanitize any future user input.** If a contact form or search feature is added,
all user-supplied input must be sanitized before rendering to the DOM. Never use
`innerHTML` with unsanitized content — use `textContent` or a sanitization library.

**Keep dependencies current.** If `package.json` or other dependency manifests are
added, enable GitHub Dependabot alerts under `Settings → Security → Code security
and analysis` to receive automated vulnerability notifications.

---

## Contact Form Security (Planned Feature)

When a contact form is added to this project, the following controls will be
implemented prior to launch:

- Form submissions routed through a third-party service (Formspree / Web3Forms /
  Netlify Forms) — maintainer email address will never be exposed in client-side code
- hCaptcha or reCAPTCHA v3 to prevent automated spam submissions
- Input length limits and server-side validation on all fields
- No user-submitted data stored client-side or committed to this repository

---

## Acknowledgements

Responsible disclosure is appreciated. Reporters who identify and privately disclose
valid vulnerabilities will be credited in the project changelog unless they prefer
to remain anonymous.

---

*This security policy was last reviewed March 2026.*
*Policy template adapted for static geospatial research projects.*
