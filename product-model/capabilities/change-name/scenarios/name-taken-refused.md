---
kind: validation
routes:
  web: Web
steps:
- text: The Admin enters a name on the member's profile
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::signed-in::user-profile
- text: Another Account already has that name
  kind: condition
  entities:
  - entity: account
    effect: reads
    facts: [Name]
  contexts:
    web:
      place: web::signed-in::user-profile
- text: The Product refuses the new name
  kind: product
  actor: admin
  entities: []
  contexts:
    web:
      place: web::signed-in::user-profile
---

# Name taken refused

## Trigger

An admin enters a name another account has.

## Outcome

The account keeps its old name and the admin is told the name is taken.
