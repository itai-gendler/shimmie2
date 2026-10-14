---
kind: primary
routes:
  web: Web
steps:
- text: The User enters the source on the post and saves
  kind: actor
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product sets the Post's source
  kind: product
  actor: user
  entities:
  - entity: post
    effect: changes
    facts: [Source]
  contexts:
    web:
      place: web::signed-in::post
---

# Set the source

## Trigger

A member knows where a post's file came from.

## Outcome

The post shows the source.
