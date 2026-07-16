# Security Policy

## Supported Versions

We release patches for security vulnerabilities. Which versions are eligible for receiving such patches depends on the CVSS v3.0 Rating:

| Version | Supported          |
| ------- | ------------------ |
| 4.0.x   | :white_check_mark: |
| 3.0.x   | :white_check_mark: |
| < 3.0   | :x:                |

## Reporting a Vulnerability

We take the security of MudraFX Ultra seriously. If you believe you have found a security vulnerability, please report it to us as described below.

**Please do NOT report security vulnerabilities through public GitHub issues.**

### How to Report

Instead, please report them via email to:

📧 **jashvs7gandhi@gmail.com**

### What to Include

Please include the following information in your report:

- Type of issue (e.g., XSS, CSRF, data exposure, etc.)
- Full paths of source file(s) related to the manifestation of the issue
- The location of the affected source code (tag/branch/commit or direct URL)
- Any special configuration required to reproduce the issue
- Step-by-step instructions to reproduce the issue
- Proof-of-concept or exploit code (if possible)
- Impact of the issue, including how an attacker might exploit it

### What to Expect

- **Acknowledgment**: We will acknowledge receipt of your vulnerability report within 48 hours
- **Investigation**: We will investigate and determine the impact and severity of the vulnerability
- **Updates**: We will provide regular updates on our progress
- **Resolution**: We will work to fix the vulnerability and release a patch
- **Credit**: We will credit you in the security advisory (unless you prefer to remain anonymous)

### Timeline

- **48 hours**: Initial acknowledgment
- **7 days**: Preliminary assessment and impact analysis
- **30 days**: Target resolution time for critical vulnerabilities
- **90 days**: Target resolution time for all other vulnerabilities

## Security Considerations

### Architecture

MudraFX Ultra is designed with security in mind:

1. **Client-Side Only**: All processing happens in the browser
2. **No Server Storage**: No user data is sent to or stored on any server
3. **Local Camera Access**: Camera feed is processed locally, never transmitted
4. **No Authentication**: No user accounts or authentication required
5. **Open Source**: Code is transparent and auditable

### Data Privacy

- **Camera Data**: Never leaves your browser
- **Gesture Data**: Processed locally, not stored
- **Settings**: Stored in browser LocalStorage only
- **Screenshots**: Saved locally to your device
- **No Analytics**: No tracking or analytics by default
- **No Cookies**: No cookies used

### Third-Party Dependencies

We use the following CDN-hosted dependencies:

- **MediaPipe Hands** (Google) - Hand tracking AI
  - URL: `https://cdn.jsdelivr.net/npm/@mediapipe/hands/`
  - Privacy: [Google Privacy Policy](https://policies.google.com/privacy)
  - Data: Processes video frames locally in browser
  
- **MediaPipe Camera Utils** (Google) - Camera management
  - URL: `https://cdn.jsdelivr.net/npm/@mediapipe/camera_utils/`
  - Privacy: [Google Privacy Policy](https://policies.google.com/privacy)

### Browser Security

MudraFX Ultra requires:

- **HTTPS or localhost** - Required for camera access (browser security requirement)
- **Modern browser** - Chrome 90+, Firefox 88+, Safari 14+, Edge 90+
- **Camera permission** - User must explicitly grant permission
- **JavaScript enabled** - Required for all functionality

### Known Security Measures

1. **Content Security Policy**: Can be added by hosting platform
2. **Secure Context**: Requires HTTPS for camera access
3. **No eval()**: No use of eval() or dynamic code execution
4. **No innerHTML**: Minimal use of innerHTML (only for gesture history)
5. **Input sanitization**: User settings are validated
6. **No external requests**: Only CDN dependencies, no API calls

## Vulnerability Disclosure Policy

We follow a coordinated disclosure process:

1. **Private Disclosure**: Reporter discloses vulnerability privately to us
2. **Investigation**: We investigate and confirm the vulnerability
3. **Fix Development**: We develop and test a fix
4. **Patch Release**: We release a patch and security advisory
5. **Public Disclosure**: After 90 days (or sooner with agreement), details can be made public

## Security Best Practices for Users

### When Deploying

1. **Always use HTTPS** - Never deploy on HTTP
2. **Keep updated** - Use the latest version
3. **Review dependencies** - Be aware of CDN dependencies
4. **Monitor console** - Check for any unexpected network requests
5. **Use secure hosting** - GitHub Pages, Netlify, Vercel all provide HTTPS

### When Using

1. **Use trusted networks** - Avoid public WiFi for sensitive use
2. **Keep browser updated** - Use latest browser version
3. **Review permissions** - Only grant camera permission when needed
4. **Clear data** - Clear LocalStorage if sharing device
5. **Check URL** - Ensure you're on the legitimate site

## Bug Bounty

Currently, we do not offer a bug bounty program. However, we greatly appreciate security researchers who responsibly disclose vulnerabilities and will:

- Credit you in our security advisories
- Add you to our contributors list
- Provide a recommendation letter (upon request)
- Consider you for future paid security work

## Security Updates

Security updates will be:

1. Released as patch versions (e.g., 4.0.0 → 4.0.1)
2. Documented in CHANGELOG.md
3. Announced in GitHub Security Advisories
4. Tagged with `security` label

## Compliance

### GDPR

MudraFX Ultra is GDPR-compliant by design:

- ✅ No personal data collected
- ✅ No cookies or tracking
- ✅ All processing is local
- ✅ No data transferred to third parties
- ✅ User has full control over their data

### CCPA

MudraFX Ultra complies with CCPA:

- ✅ No personal information collected
- ✅ No sale of user data
- ✅ No sharing with third parties
- ✅ Users can delete LocalStorage data anytime

### COPPA

MudraFX Ultra is safe for children:

- ✅ No data collection
- ✅ No user accounts
- ✅ No advertising
- ✅ No third-party tracking

## Contact

For security-related questions or concerns:

📧 **Email**: [jashvs7gandhi@gmail.com](mailto:jashvs7gandhi@gmail.com)

**PGP Key**: Available upon request

**Response Time**: Within 48 hours

## Acknowledgments

We would like to thank the following security researchers who have responsibly disclosed vulnerabilities:

- *(None yet - be the first!)*

## Resources

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [CWE/SANS Top 25](https://cwe.mitre.org/top25/)
- [Google Web Fundamentals - Security](https://developers.google.com/web/fundamentals/security)
- [MDN Web Security](https://developer.mozilla.org/en-US/docs/Web/Security)

---

**Last Updated**: January 2024

**Policy Version**: 1.0

This security policy is inspired by GitHub's security policy template and the disclose.io policy framework.
