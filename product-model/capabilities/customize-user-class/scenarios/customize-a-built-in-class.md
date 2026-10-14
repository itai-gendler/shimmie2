---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Edit on a built-in class
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::board-admin::permission-manager
- text: The Product copies the class's parent, description and own permissions into the board and opens it
  kind: product
  actor: admin
  entities:
  - entity: user-class
    effect: changes
    from: Built-in
    to: Customized
    facts: [Parent class, Description, Permissions]
  - entity: board
    effect: reads
    facts: []
  contexts:
    web:
      place: web::board-admin::user-class
---

# Customize a built-in class

## Trigger

An admin wants members of the User class to be able to delete their own posts.

## Outcome

The class is customized and its editor opens with its current settings.
