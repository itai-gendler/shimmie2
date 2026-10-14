---
kind: primary
routes:
  web: Web
steps:
- text: The Admin clears Comments Locked on the post and saves
  kind: actor
  actor: admin
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
- text: The Product unlocks the Post's comments
  kind: product
  actor: admin
  entities:
  - entity: post
    effect: changes
    facts: [Comments locked]
  - entity: comment
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
---

# Unlock a post's comments

## Trigger

A post may be discussed again.

## Outcome

Members can comment on the post again.
