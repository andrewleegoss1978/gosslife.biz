# gosslife.biz Runbook

Last updated: 2026-04-07
Owner: Andrew Goss

## Purpose

Central reference for gosslife.biz hosting, DNS, and GitHub Pages settings.

## Hosting Architecture

- Domain registrar/DNS: Squarespace Domains
- Website host: GitHub Pages
- GitHub account: andrewleegoss1978
- GitHub repository: https://github.com/andrewleegoss1978/gosslife.biz
- Pages source: branch main, path /

## Published Pages

- Home: http://gosslife.biz/
- Privacy policy: http://gosslife.biz/privacy/

## GitHub Pages Configuration (current)

- Pages status: built
- CNAME: gosslife.biz
- Public repo: true
- HTTPS enforced: false (pending certificate issuance)

## Required DNS Records (Squarespace)

Apex A records (host @):
- 185.199.108.153
- 185.199.109.153
- 185.199.110.153
- 185.199.111.153

Recommended for www:
- CNAME host www -> andrewleegoss1978.github.io

Keep existing email records unchanged:
- Google Workspace MX/TXT/DKIM/SPF records currently configured in Squarespace should remain as-is.

## Site Files in Repo

- index.html
- privacy/index.html
- CNAME

## Verification Commands

Run from any terminal:

- dig +short gosslife.biz A
- dig +short www.gosslife.biz CNAME
- curl -I http://gosslife.biz
- curl -I https://gosslife.biz
- curl -I https://gosslife.biz/privacy/

## Expected Behavior During DNS/SSL Propagation

- HTTP may work before HTTPS.
- HTTPS can temporarily fail with certificate mismatch until GitHub certificate provisioning completes.
- Once certificate is issued, enable "Enforce HTTPS" in GitHub Pages settings.

## Operational Checklist

1. Confirm DNS A records for @ point to the 4 GitHub Pages IPs.
2. Confirm Pages status is built in GitHub repository settings.
3. Confirm custom domain is set to gosslife.biz.
4. Wait for certificate issuance.
5. Enable Enforce HTTPS.
6. Verify:
   - https://gosslife.biz
   - https://gosslife.biz/privacy/

## Yahoo Developer Access Dependency

For Yahoo Mail API access form submission, use:
- Product URL: https://gosslife.biz
- Privacy URL: https://gosslife.biz/privacy/
