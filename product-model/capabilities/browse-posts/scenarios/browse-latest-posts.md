---
kind: primary
routes:
  web: Web
steps:
- text: Anonymous opens Posts
  kind: actor
  actor: anonymous
  entities:
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::visitor::post-list
- text: The Product lists approved Posts newest first with popular Tags
  kind: product
  actor: anonymous
  entities:
  - entity: post
    effect: reads
    facts: [File, Tags, Rating]
  - entity: tag
    effect: reads
    facts: [Name, Post count]
  contexts:
    web:
      place: web::visitor::post-list
- text: The page size follows the board's setting
  kind: condition
  entities:
  - entity: board
    effect: reads
    facts: [Posts per page]
  contexts:
    web:
      place: web::visitor::post-list
---

# Browse the latest posts

## Trigger

A visitor opens the post list.

## Outcome

The visitor sees the newest approved posts they may see, a page at a time, with popular tags.

## Edge cases

- A board with no posts yet shows an introduction instead of an empty list.
