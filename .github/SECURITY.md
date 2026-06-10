# Security Policy

## Reporting a vulnerability

Do not open a public issue for security vulnerabilities.

Report security concerns directly to the project owner or technical lead.

Include:

- Affected project or repository
- Description of the issue
- Steps to reproduce, if applicable
- Potential impact
- Screenshots or logs, if relevant

## Secrets and credentials

Never commit:

- Passwords
- API keys
- Connection strings
- Tokens
- Private certificates
- Production `.env` files

If a secret is committed by mistake, notify the technical lead immediately so the secret can be rotated.