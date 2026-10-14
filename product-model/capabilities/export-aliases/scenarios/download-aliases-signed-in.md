---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Download as CSV
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::aliases
- text: The Product sends every Alias as a CSV file
  kind: product
  actor: user
  entities:
  - entity: alias
    effect: reads
    facts: [Old tag, New tags]
  contexts:
    web:
      place: web::signed-in::aliases
---

# Download aliases while signed in

## Trigger

A member wants a copy of the aliases.

## Outcome

A CSV file lists every alias.
