---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Revert to Default on a customized class
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::board-admin::permission-manager
- text: The Product drops the board's copy of the User class
  kind: product
  actor: admin
  entities:
  - entity: user-class
    effect: changes
    from: Customized
    to: Built-in
    facts: [Parent class, Description, Permissions]
  - entity: user
    effect: reads
    facts: []
  - entity: board
    effect: reads
    facts: []
  contexts:
    web:
      place: web::board-admin::permission-manager
---

# Revert to default

## Trigger

An admin wants a customized class back as shipped.

## Outcome

The class has its built-in settings again.

## Edge cases

- A class from the operator's configuration file offers Revert to File instead, with the same effect.
