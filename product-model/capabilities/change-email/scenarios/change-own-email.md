---
kind: primary
routes:
  web: Web
steps:
- text: The User enters a new address on their profile
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::user-profile
- text: The Product sets the Account's email address
  kind: product
  actor: user
  entities:
  - entity: account
    effect: changes
    facts: [Email]
  contexts:
    web:
      place: web::signed-in::user-profile
---

# Change own email

## Trigger

A member's email address changes.

## Outcome

The account keeps the new address.
