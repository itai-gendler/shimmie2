---
kind: validation
routes:
  web: Web
steps:
- text: The User adds an invalid tag and saves
  kind: actor
  actor: user
  entities:
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product refuses the tags and leaves the Post unchanged
  kind: product
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: [Tags]
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
---

# Invalid tag refused

## Trigger

A member adds a tag that starts with a minus, contains *, or is longer than 255 characters.

## Outcome

The post's tags are unchanged and the member is told why.
