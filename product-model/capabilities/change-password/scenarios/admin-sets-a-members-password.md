---
kind: primary
routes:
  web: Web
steps:
- text: The Admin enters a new password twice on the member's profile
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::signed-in::user-profile
- text: The Product sets that Account's password
  kind: product
  actor: admin
  entities:
  - entity: account
    effect: changes
    facts: [Password]
  contexts:
    web:
      place: web::signed-in::user-profile
---

# Admin sets a member's password

## Trigger

A member cannot sign in and asks an admin for help.

## Outcome

The member's account has the password the admin chose.
