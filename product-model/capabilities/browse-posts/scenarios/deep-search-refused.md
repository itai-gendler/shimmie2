---
kind: validation
routes:
  web: Web
steps:
- text: Anonymous asks for a page beyond the search result limit
  kind: actor
  actor: anonymous
  entities: []
  contexts:
    web:
      place: web::visitor::post-list
- text: The board limits search results and the visitor's class lacks Big search
  kind: condition
  entities:
  - entity: board
    effect: reads
    facts: [Search result limit, Anonymous tag limit]
  contexts:
    web:
      place: web::visitor::post-list
- text: The Product refuses the page and asks for more specific terms
  kind: product
  actor: anonymous
  entities: []
  contexts:
    web:
      place: web::visitor::post-list
---

# Search beyond the result limit refused

## Trigger

A visitor pages past the search result limit, or combines more tags than the board allows.

## Outcome

The page is refused with a request to use more specific search terms.
