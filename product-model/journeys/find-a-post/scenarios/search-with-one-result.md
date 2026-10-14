---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: Anonymous searches for tags
  kind: actor
  actor: anonymous
  capability: browse-posts
  entities:
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::visitor::post-list
- text: The Product finds exactly one matching Post and opens it
  kind: product
  actor: anonymous
  capability: browse-posts
  entities:
  - entity: post
    effect: reads
    facts: [Tags]
  contexts:
    web:
      place: web::visitor::post-list
- text: Anonymous looks at the Post
  kind: actor
  actor: anonymous
  capability: view-post
  entities:
  - entity: post
    effect: reads
    facts: [File, Tags]
  contexts:
    web:
      place: web::visitor::post
---

# Search with one result

## Trigger

A visitor searches for tags that only one post carries.

## Outcome

The post opens directly instead of a list of one.
