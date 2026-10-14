---
kind: primary
routes:
  web: Web
steps:
- text: Anonymous opens Tags
  kind: actor
  actor: anonymous
  entities:
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::visitor::tags
- text: The Product lists Tags with their post counts
  kind: product
  actor: anonymous
  entities:
  - entity: tag
    effect: reads
    facts: [Name, Post count]
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::visitor::tags
---

# Browse the tag map

## Trigger

A visitor wants to see what the board is about.

## Outcome

The visitor sees the tags in use, the more used ones more prominent.
