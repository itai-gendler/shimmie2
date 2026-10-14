---
kind: primary
routes:
  web: Web
steps:
- text: The Admin sets permissions to granted, denied or inherited and chooses Save Permissions
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::board-admin::user-class
- text: The Product saves the User class's permissions
  kind: product
  actor: admin
  entities:
  - entity: user-class
    effect: changes
    facts: [Permissions]
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::board-admin::user-class
---

# Set permissions

## Trigger

An admin decides what a class may do.

## Outcome

Members of the class hold the new permissions; inherited ones follow the parent.
