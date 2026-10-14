---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Admin creates a class under a parent
  kind: actor
  actor: admin
  capability: create-user-class
  entities: []
  contexts:
    web:
      place: web::board-admin::permission-manager
- text: The Product creates the User class and opens it
  kind: product
  actor: admin
  capability: create-user-class
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
- text: The Admin sets the class's permissions and saves
  kind: actor
  actor: admin
  capability: change-class-permissions
  entities:
  - entity: user-class
    effect: changes
    facts: [Permissions]
  contexts:
    web:
      place: web::board-admin::user-class
---

# Create a class and set its permissions

## Trigger

An admin needs a Moderator class.

## Outcome

The class exists and grants the permissions the admin set.
