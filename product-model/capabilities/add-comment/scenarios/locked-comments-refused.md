---
kind: validation
routes:
  web: Web
steps:
- text: The User opens a post
  kind: actor
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Post's comments are locked
  kind: condition
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: [Comments locked]
  - entity: comment
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product offers no comment box and refuses comments on the post
  kind: product
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: []
  - entity: comment
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
---

# Locked comments refused

## Trigger

A member tries to comment on a post whose comments are locked.

## Outcome

No comment is added; the post offers no comment box.
