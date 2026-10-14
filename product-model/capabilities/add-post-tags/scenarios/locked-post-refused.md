---
kind: validation
routes:
  web: Web
steps:
- text: The User edits the tags of a post and saves
  kind: actor
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: []
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Post is locked
  kind: condition
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: [Locked]
  contexts:
    web:
      place: web::signed-in::post
- text: The Product refuses the edit
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::post
---

# Locked post refused

## Trigger

A member tries to edit a post an admin has locked.

## Outcome

Nothing changes and the member is told an admin has locked the post.
