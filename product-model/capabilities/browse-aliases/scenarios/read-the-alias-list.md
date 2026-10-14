---
kind: primary
routes:
  web: Web
steps:
- text: Anonymous opens Aliases
  kind: actor
  actor: anonymous
  entities:
  - entity: alias
    effect: reads
    facts: []
  contexts:
    web:
      place: web::visitor::aliases
- text: The Product lists the Aliases
  kind: product
  actor: anonymous
  entities:
  - entity: alias
    effect: reads
    facts: [Old tag, New tags]
  contexts:
    web:
      place: web::visitor::aliases
---

# Read the alias list

## Trigger

A visitor wonders why a tag changes when used.

## Outcome

The visitor sees each old tag and what replaces it.
