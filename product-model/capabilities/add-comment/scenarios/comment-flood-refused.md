---
kind: validation
routes:
  web: Web
steps:
- text: The User submits a comment
  kind: actor
  actor: user
  entities:
  - entity: comment
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The member's address reached the comment limit within the window, or the post already has the same comment
  kind: condition
  actor: user
  entities:
  - entity: board
    effect: reads
    facts: [Comment limit, Comment limit window]
  - entity: comment
    effect: reads
    facts: [Text]
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product refuses the comment
  kind: product
  actor: user
  entities:
  - entity: comment
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
---

# Comment flood refused

## Trigger

A member comments too often, or repeats a comment already on the post.

## Outcome

No comment is added and the member is asked to wait or be more original.
