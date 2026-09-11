# Contributing catalog facts

Submit narrowly scoped changes to public data with evidence from the provider's
official documentation. Use public documentation links and record when the fact
was checked. Keep model identity, provider offering identity and wire model
identity distinct; an attractive display name is not evidence for an API ID.

## Review checklist

- Include only publicly documented model facts. Do not infer missing capability,
  pricing or availability claims from another member of a model family.
- Preserve exact execution requirements, units, currencies and applicability.
  Unknown pricing is unknown, not zero. Do not invent a generic wire protocol.
- Follow the existing schema vocabulary and required references. New vocabulary
  requires a separately versioned schema and client support.
- Keep records deterministic and reviewable. Do not make unrelated formatting,
  deletion or lifecycle changes in a model addition.
- Include no secrets, private URLs, endpoint settings, account identifiers,
  application configuration, logs, conversations or private source code.
- Do not add binaries, executables, archives, symlinks, submodules or Git history
  copied from another repository.

Automated validation and human review are both required. A passing check is not
proof that all possible sensitive information is absent.

## Source changes are not releases

Ordinary contributions update authoring data. Do not hand-edit signed manifests,
release revisions, detached signatures or existing content-addressed targets.
Promotion must bind an exact reviewed source commit to independently validated
per-schema bundles. Signing, publication, key changes and feed retirement require
separate maintainer authorization.

Pull-request validation must remain read-only and receive no signing material
or protected deployment environment. Release deployment consumes only the
reviewed artifact layout and must not execute untrusted pull-request code with
write privileges.
