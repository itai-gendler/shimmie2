---
kind: primary
routes:
  web: Web
steps:
- text: The Admin ticks Metadata Locked on the post and saves
  kind: actor
  actor: admin
  entities:
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product locks the Post
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

# Lock a post

## Trigger

A post keeps being tagged wrongly.

## Outcome

The post is locked: members can no longer change its tags, source or rating.
