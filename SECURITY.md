# Security policy

## Supported versions

| Version | Supported         |
| ------- | ----------------- |
| 2.x     | ✅ Security fixes |
| 1.x     | ❌ Upgrade to 2.x |

## Reporting a vulnerability

**Please don't open a public issue.**

1. Use GitHub's private reporting: [report a vulnerability](https://github.com/braqon-dev/express-version-api/security/advisories/new).
2. If you can't, email **security@braqon.dev** with the subject `SECURITY: express-version-api`.

Include the affected version, a minimal reproduction and the impact you expect. Reports are welcome in English or Spanish.

## What to expect

- Acknowledgement within **3 business days**.
- An initial assessment within **7 days**.
- A fix or mitigation for confirmed issues as soon as possible, coordinated with you before anything is made public.
- Credit in the advisory and the changelog, if you want it.

## Scope

In scope: the code published to npm, JSR and GitHub Packages, and this repository's release workflows.

Out of scope: vulnerabilities in Express itself (report them to [Express](https://github.com/expressjs/express/security)) and in development-only dependencies that never reach the published package.

## How releases are protected

- Published from GitHub Actions with npm trusted publishing (OIDC) and signed provenance. No long-lived publish tokens exist.
- `main` and `develop` require signed commits and a passing CI before merge.
- CodeQL, secret scanning with push protection, and Dependabot security alerts are enabled.
- Zero runtime dependencies.

You can verify a release with `npm audit signatures`.
