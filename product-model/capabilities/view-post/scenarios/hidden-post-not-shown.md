---
kind: validation
routes:
  web: Web
steps:
- text: Anonymous opens a post
  kind: actor
  actor: anonymous
  entities:
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::visitor::post
- text: The Post is pending approval, or its rating is not among those the visitor's class may see
  kind: condition
  actor: anonymous
  entities:
  - entity: board
    effect: reads
    facts: [Ratings each class may see]
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::visitor::post
- text: The Product sends the visitor to the front page instead
  kind: product
  actor: anonymous
  entities: []
  contexts:
    web:
      place: web::visitor::post
---

# Hidden post not shown

## Trigger

A visitor opens a post that is pending approval, or whose rating their class may not see.

## Outcome

The post is not shown and the visitor lands on the front page; its file is refused too.
