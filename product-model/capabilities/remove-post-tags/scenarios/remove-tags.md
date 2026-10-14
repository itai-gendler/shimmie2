---
kind: primary
routes:
  web: Web
steps:
- text: The User deletes tags from the post's tag list and saves
  kind: actor
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: []
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product sets the Post's remaining tags
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
      place: web::signed-in::post
---

# Remove tags

## Trigger

A member sees a wrong tag on a post.

## Outcome

The post no longer carries the tag and its count drops.
