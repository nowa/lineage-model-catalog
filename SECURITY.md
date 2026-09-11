# Security

Do not include secrets, private configuration, account identifiers, private
source, conversation content or unredacted logs in a public issue or pull request.

## Reporting a vulnerability

Use this repository's private vulnerability reporting facility if it is enabled.
If it is unavailable, request a private contact from the repository owner without
posting exploit details or sensitive material. Never assume an ordinary issue is
private. Security-reporting availability must be checked before the first release.

Provide the affected public revision, expected trust property and a minimal
synthetic reproduction when possible. Use invented identities and locally
generated fixture data. Do not send production keys or other people's data.

## Accidental sensitive publication

Stop further distribution, notify the owner privately and rotate or revoke any
exposed credential through its issuing service. Removing a file from the current
branch does not remove it from history, forks, caches or published artifacts.
History remediation and release revocation require coordinated maintainer review.

## Trust boundaries

A data or schema change does not authorize code execution, model selection,
new network destinations, a signing key or a release. Workflow changes are
security-sensitive. Schema validation, signature verification, source review and
deployment protection are separate controls; no single one substitutes for the
others.

Before releasing, maintainers must verify branch and environment protection,
private reporting, key custody, supported feeds and artifact provenance.
