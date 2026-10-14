---
kind: primary
routes:
  web: Web
steps:
- text: The User filters the alias list by a tag
  kind: actor
  actor: user
  entities:
  - entity: tag
    effect: reads
    facts: []
  - entity: alias
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::aliases
- text: The Product lists the matching Aliases
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

# Filter aliases

## Trigger

A member looks for the aliases of one tag.

## Outcome

The member sees the matching aliases.
