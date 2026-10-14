---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Admin chooses Edit on a built-in class
  kind: actor
  actor: admin
  capability: customize-user-class
  entities: []
  contexts:
    web:
      place: web::board-admin::permission-manager
- text: The Product copies the User class into the board and opens it
  kind: product
  actor: admin
  capability: customize-user-class
  entities:
  - entity: user-class
    effect: changes
    from: Built-in
    to: Customized
    facts: [Parent class, Description, Permissions]
  - entity: user
    effect: reads
    facts: []
  - entity: board
    effect: reads
    facts: []
  contexts:
    web:
      place: web::board-admin::user-class
- text: The Admin grants the permission and saves
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

# Customize a class and set its permissions

## Trigger

An admin wants Users to delete their own posts.

## Outcome

The User class is customized and grants Delete own post.
