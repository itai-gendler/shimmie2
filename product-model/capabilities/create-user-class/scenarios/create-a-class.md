---
kind: primary
routes:
  web: Web
steps:
- text: The Admin enters a name, a parent class and a description and chooses Create
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::board-admin::permission-manager
- text: The Product creates the User class and opens it
  kind: product
  actor: admin
  entities:
  - entity: user-class
    effect: creates
    to: Custom
    facts: [Name, Parent class, Description]
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::board-admin::user-class
---

# Create a class

## Trigger

An admin needs a role such as Moderator.

## Outcome

The class exists, inheriting everything from its parent, and its editor opens.
