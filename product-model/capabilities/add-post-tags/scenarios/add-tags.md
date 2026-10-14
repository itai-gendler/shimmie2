---
kind: primary
routes:
  web: Web
steps:
- text: The User adds tags to the post's tag list and saves
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
- text: The Product replaces aliased tags and sets the Post's tags
  kind: product
  actor: user
  entities:
  - entity: post
    effect: changes
    facts: [Tags]
  - entity: alias
    effect: reads
    facts: [Old tag, New tags]
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
---

# Add tags

## Trigger

A member sees a post missing tags.

## Outcome

The post carries the new tags and each tag's count grows.

## Edge cases

- Metatags in the list, such as rating=s or source=…, set those facts instead of becoming tags.
