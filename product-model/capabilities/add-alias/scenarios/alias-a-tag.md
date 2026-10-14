---
kind: primary
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
- text: The Product retags every Post carrying the old tag
  kind: product
  actor: admin
  entities:
  - entity: post
    effect: changes
    facts: [Tags]
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::aliases
- text: The Product adds the Alias
  kind: product
  actor: admin
  entities:
  - entity: alias
    effect: creates
    facts: [Old tag, New tags]
  contexts:
    web:
      place: web::signed-in::aliases
---

# Alias a tag

## Trigger

Two tags mean the same thing.

## Outcome

The old tag is replaced by the new one on every post and wherever it is used from now on.
