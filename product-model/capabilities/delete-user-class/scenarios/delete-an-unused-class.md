---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Delete on a custom class with no members
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::board-admin::permission-manager
- text: The Product deletes the User class
  kind: product
  actor: admin
  entities:
  - entity: user-class
    effect: removes
    from: Custom
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::board-admin::permission-manager
---

# Delete an unused class

## Trigger

A custom class is no longer needed and has no members.

## Outcome

The class is gone.
