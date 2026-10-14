---
kind: primary
routes:
  web: Web
steps:
- text: The Admin enters the tags to replace and their replacement in Mass Tag Edit
  kind: actor
  actor: admin
  entities:
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::board-admin::board-admin
- text: The Product retags each Post carrying the old tags
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
      place: web::board-admin::board-admin
---

# Merge into an existing tag

## Trigger

Posts already use the replacement tag.

## Outcome

Every post that had the old tags carries the replacement instead.
