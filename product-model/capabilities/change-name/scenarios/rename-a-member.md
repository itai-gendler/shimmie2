---
kind: primary
routes:
  web: Web
steps:
- text: The Admin enters a new name on the member's profile
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::signed-in::user-profile
- text: The Product checks the name is valid and free, then renames the Account
  kind: product
  actor: admin
  entities:
  - entity: account
    effect: changes
    facts: [Name]
  contexts:
    web:
      place: web::signed-in::user-profile
---

# Rename a member

## Trigger

An admin needs a member to have a different username.

## Outcome

The account has the new name.
