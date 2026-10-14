---
kind: primary
routes:
  web: Web
steps:
- text: The Admin enters another member's name as uploader and saves
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product credits the Post to that Account
  kind: product
  actor: admin
  entities:
  - entity: post
    effect: changes
    facts: [Uploader]
  - entity: account
    effect: reads
    facts: [Name]
  contexts:
    web:
      place: web::signed-in::post
---

# Credit a post to another account

## Trigger

A post was uploaded on someone else's behalf.

## Outcome

The post shows the new uploader and counts toward their posts.
