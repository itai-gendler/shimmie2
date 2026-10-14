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
- text: The comment is empty, over 9000 characters, too repetitive, or its form is out of date
  kind: condition
  entities:
  - entity: comment
    effect: reads
    facts: [Text]
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

# Unacceptable comment refused

## Trigger

A member submits an empty, overlong or repetitive comment, or one from a form left open for hours.

## Outcome

No comment is added and the member is told why.
