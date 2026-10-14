---
kind: validation
routes:
  web: Web
steps:
- text: The Admin enters the old tag and the new tag
  kind: actor
  actor: admin
  entities:
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::aliases
- text: The old tag already has an Alias, or the new tag is itself aliased
  kind: condition
  entities:
  - entity: alias
    effect: reads
    facts: [Old tag, New tags]
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::aliases
- text: The Product refuses the alias
  kind: product
  actor: admin
  entities:
  - entity: alias
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::aliases
---

# Conflicting alias refused

## Trigger

An admin aliases a tag that is already aliased, or to a tag that is itself an alias.

## Outcome

No alias is added and the admin is told which alias is in the way.
