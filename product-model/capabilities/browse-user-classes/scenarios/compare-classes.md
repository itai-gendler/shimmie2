---
kind: primary
routes:
  web: Web
steps:
- text: The Admin opens the Permission Manager
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::board-admin::permission-manager
- text: The Product lists every User class with its permissions and members
  kind: product
  actor: admin
  entities:
  - entity: user-class
    effect: reads
    facts: [Name, Parent class, Description, Permissions, Member count]
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::board-admin::permission-manager
---

# Compare classes

## Trigger

An admin wants to know who may do what.

## Outcome

The admin sees each class and each permission's value per class.
