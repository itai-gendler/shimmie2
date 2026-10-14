---
kind: primary
routes:
  web: Web
steps:
- text: Anonymous chooses Download as CSV
  kind: actor
  actor: anonymous
  entities: []
  contexts:
    web:
      place: web::visitor::aliases
- text: The Product sends every Alias as a CSV file
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

# Download aliases

## Trigger

Someone wants a copy of the aliases.

## Outcome

A CSV file lists every alias.
