---
kind: primary
routes:
  web: Web
steps:
- text: The Admin enters the old tag and its replacement in Mass Tag Edit
  kind: actor
  actor: admin
  entities:
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::board-admin::board-admin
- text: No Post carries the replacement yet
  kind: condition
  actor: admin
  entities:
  - entity: post
    effect: reads
    facts: [Tags]
  contexts:
    web:
      place: web::board-admin::board-admin
- text: The Product renames the Tag in place
  kind: product
  actor: admin
  entities:
  - entity: tag
    effect: changes
    facts: [Name]
  contexts:
    web:
      place: web::board-admin::board-admin
---

# Rename a tag

## Trigger

A tag is misspelled and no post yet uses the correct spelling.

## Outcome

The tag has its new name on every post.
