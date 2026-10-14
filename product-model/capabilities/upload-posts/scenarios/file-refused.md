---
kind: validation
routes:
  web: Web
steps:
- text: The User uploads a file
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::upload
- text: The file is over the size limit, unsupported, empty or corrupt
  kind: condition
  entities:
  - entity: board
    effect: reads
    facts: [Max size per file]
  contexts:
    web:
      place: web::signed-in::upload
- text: The Product reports why the file was refused
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::upload
---

# Unusable file refused

## Trigger

A member uploads a file that is too large, of an unsupported type, empty or corrupt, or the board's disk is nearly full.

## Outcome

That file does not become a post and the member is told why; other files in the same upload are unaffected.
