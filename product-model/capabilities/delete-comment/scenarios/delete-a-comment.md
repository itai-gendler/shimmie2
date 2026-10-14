---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Del on the comment and confirms
  kind: actor
  actor: admin
  entities:
  - entity: comment
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product deletes the Comment
  kind: product
  actor: admin
  entities:
  - entity: comment
    effect: removes
  contexts:
    web:
      place: web::signed-in::post
---

# Delete a comment

## Trigger

An admin finds an unwanted comment.

## Outcome

The comment is gone.
