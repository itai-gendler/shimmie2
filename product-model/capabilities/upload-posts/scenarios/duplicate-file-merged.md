---
kind: edge
routes:
  web: Web
steps:
- text: The User uploads a file with tags
  kind: actor
  actor: user
  entities:
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::upload
- text: A Post already holds the same file and upload collisions merge
  kind: condition
  actor: user
  entities:
  - entity: board
    effect: reads
    facts: [Upload collisions]
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::upload
- text: The Product adds the given tags to the existing Post
  kind: product
  actor: user
  entities:
  - entity: post
    effect: changes
    facts: [Tags]
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::upload
---

# Duplicate file merged

## Trigger

A member uploads a file that is already a post, on a board that merges upload collisions.

## Outcome

No new post is created; the existing post gains the tags given with the upload.
