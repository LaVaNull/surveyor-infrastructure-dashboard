# Security policy

## Supported deployment

Surveyor is intended for private-network use. Internet exposure is not supported without trusted HTTPS, authentication, rate limiting, and an independent security review.

## Reporting a vulnerability

Do not include credentials, private keys, wallet identifiers, internal addresses, logs, database copies, or device inventories in a public report. Share only a minimal reproduction through a private channel designated by the repository owner.

## Secret handling

- Store credentials in a root-owned environment file with mode `600`.
- Keep monitoring private keys outside the source tree.
- Restrict monitoring keys with forced commands and source/network controls where practical.
- Never commit known-host files, databases, backups, logs, or API captures.
- Rotate a credential immediately if it enters Git history, even if a later commit removes it.

## Access controls

- Use a dedicated unprivileged account for the web service.
- Keep the application bound to loopback behind the reverse proxy.
- Permit dashboard and SSH access only from approved networks.
- Disable SSH passwords, forwarding, tunneling, and X11.
- Use an audit-only virtualization token.
- Keep restart, backup, and firewall management outside the application process.

## Before publishing

Run a secret scanner against the full Git history, inspect binary files and generated artifacts, replace real infrastructure values with synthetic fixtures, and verify third-party artwork licenses.

