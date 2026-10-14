---
kind: edge
routes:
  web: Web
steps:
- text: The User clears the post's tag list and saves
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
- text: The Product tags the Post tagme
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

# Remove every tag

## Trigger

A member clears the whole tag list of a post.

## Outcome

The post is tagged tagme so it can be found and tagged again.
