---
kind: validation
routes:
  web: Web
steps:
- text: The Admin submits the import without a file
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::signed-in::aliases
- text: The Product refuses the import
  kind: product
  actor: admin
  entities: []
  contexts:
    web:
      place: web::signed-in::aliases
---

# No file refused

## Trigger

An admin submits the import without a file.

## Outcome

Nothing is imported and the admin is told no file was given.
