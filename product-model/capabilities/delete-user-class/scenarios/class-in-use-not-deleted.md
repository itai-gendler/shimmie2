---
kind: validation
routes:
  web: Web
steps:
- text: The Admin looks for Delete on a class
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::board-admin::permission-manager
- text: The User class has members or is built in
  kind: condition
  entities:
  - entity: user-class
    effect: reads
    facts: [Member count]
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::board-admin::permission-manager
- text: The Product offers no deletion for the class
  kind: product
  actor: admin
  entities: []
  contexts:
    web:
      place: web::board-admin::permission-manager
---

# Class in use not deleted

## Trigger

An admin wants to delete a class that still has members, or a built-in class.

## Outcome

The class stays; the Permission Manager offers no Delete for it.
