---
kind: primary
routes:
  web: Web
steps:
- text: The Admin ticks Comments Locked on the post and saves
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
- text: The Product locks the Post's comments
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

# Lock a post's comments

## Trigger

A discussion on a post gets out of hand.

## Outcome

Members can no longer comment on the post; existing comments stay.
