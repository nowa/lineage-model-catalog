# Lineage model catalog

Public model facts and versioned, signed catalog artifacts for compatible Lineage
clients. This repository contains data, schemas and contribution documentation;
it is not the Lineage application source repository.

## What the catalog does

The catalog describes provider offerings, supported input and output capabilities,
execution requirements, lifecycle information and sourced pricing facts. A
compatible client can learn about a new offering without an application release.
A new protocol or unsupported execution requirement still needs client support.

The catalog does not rank models, recommend a "best" model, or select a model for
a user. Users choose their own models for supported purposes. Connections,
authentication, private model definitions and endpoint configuration stay local.
A catalog update must not change those choices or silently enable voice.

## Files and trust

- `catalog/catalog.v1.json`: reviewed authoring data, not an installation artifact.
- `schema/`: public JSON Schema descriptions.
- `v1/stable/manifest.json` and `manifest.sig`: versioned release metadata and
  detached signature envelope.
- `targets/sha256/`: immutable, content-addressed catalog payloads.

Clients authenticate exact manifest bytes with a locally trusted key, validate
target bytes and semantics, and enforce freshness and rollback protections.
Passing JSON Schema validation alone proves none of these trust properties.
Editing source data or merging a pull request does not authorize a release.

A schema-versioned feed must keep its contract. Future feeds coexist with
supported older feeds; unsupported execution requirements must never be removed
from an offering to make it appear compatible. Referenced targets are retained.
Feed retirement requires an explicit support-policy review.

## Contributions and safety

### Reading limits and prices

Context-window and maximum-output limits belong to an offering's operation
capabilities. An omitted or null limit is unknown, not unlimited. A shared model
name does not establish the same limits on every service or deployment.

Price cards retain currency, billing meters and units, cache rates, applicable
regions/service tiers, validity intervals, context tiers and source evidence.
Card presence does not establish eligibility for a particular account or make
unsupported billing meters free. Missing prices are unknown, not zero. Compare
only rates whose units and conditions match the intended use.

Publicly documented enterprise offers can be included when their eligibility and
pricing conditions fit the schema and have public evidence. Confidential quotes,
private model definitions and negotiated account rates stay in the user's local
configuration; they are not contributed to this repository.

The manifest's freshness deadline and an individual price card's validity are
independent. Renewing a manifest does not extend a promotion or certify that a
provider's prices have remained unchanged.

### Safe contributions

Read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting changes. Use
[SECURITY.md](SECURITY.md) for security concerns. Do not submit application
configuration, account details, conversations, logs, keys or private source.

Pricing and availability may change independently at the provider. Sourced
catalog facts are not a service guarantee or a recommendation to purchase.

## Validation and publication

The read-only validation workflow checks public file inventory, schema shape,
references and deterministic authoring JSON. It uses pinned generic tools and
does not authenticate a release. Source contributions do not require a signed
release envelope.

Pages deployment is manually requested for the main branch and requires approval
through the protected deployment environment. The read-only build retains all
allowed content-addressed targets and passes only feed metadata and targets to
the deployment job. Independently reviewed signatures and release authorization
are prerequisites, not outcomes of this build. Configure and verify repository
and environment protections before enabling publication.

The current supported feed is v1/stable. Its schema vocabulary stays frozen;
additional feeds and retirement require explicit support-policy review. A
publication build rejects unrecognized feeds rather than silently dropping them.

## Public-data license

The public catalog materials are offered under CC0-1.0; see [LICENSE](LICENSE).
This declaration does not license or disclose the private Lineage application.
Provider names and trademarks remain their owners' property.
