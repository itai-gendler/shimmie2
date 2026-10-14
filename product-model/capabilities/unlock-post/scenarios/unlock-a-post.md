---
kind: primary
routes:
  web: Web
steps:
- text: The Admin clears Metadata Locked on the post and saves
  kind: actor
  actor: admin
  entities:
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product unlocks the Post
  kind: product
  actor: admin
  entities:
  - entity: post
    effect: changes
    facts: [Locked]
  contexts:
    web:
      place: web::signed-in::post
---

# Unlock a post

## Trigger

A locked post may be edited again.

## Outcome

Members can edit the post's information again.
