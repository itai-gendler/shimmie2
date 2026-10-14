---
kind: validation
routes:
  web: Web
steps:
- text: The User uploads a file
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::upload
- text: A Post already holds the same file and upload collisions are errors
  kind: condition
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: [File]
  - entity: board
    effect: reads
    facts: [Upload collisions]
  contexts:
    web:
      place: web::signed-in::upload
- text: The Product reports the existing post for that file
  kind: product
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::upload
---

# Duplicate file refused

## Trigger

A member uploads a file whose content is already a post, on a board that treats upload collisions as errors.

## Outcome

No new post is created and the member is told which post already has the file.
