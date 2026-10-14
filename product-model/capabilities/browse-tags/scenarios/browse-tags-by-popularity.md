---
kind: primary
routes:
  web: Web
steps:
- text: The User opens Tags by Popularity
  kind: actor
  actor: user
  entities:
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::tags
- text: The Product lists Tags ordered by post count
  kind: product
  actor: user
  entities:
  - entity: tag
    effect: reads
    facts: [Name, Post count]
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::tags
---

# Browse tags by popularity

## Trigger

A member wants the most used tags.

## Outcome

The member sees tags grouped by how many posts carry them.
