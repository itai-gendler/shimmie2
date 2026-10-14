---
kind: primary
routes:
  web: Web
steps:
- text: The Admin picks a parent, edits the description and saves
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::board-admin::user-class
- text: The Product saves the User class
  kind: product
  actor: admin
  entities:
  - entity: user-class
    effect: changes
    facts: [Parent class, Description]
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::board-admin::user-class
---

# Change parent and description

## Trigger

An admin restructures the class tree.

## Outcome

The class inherits from its new parent.
