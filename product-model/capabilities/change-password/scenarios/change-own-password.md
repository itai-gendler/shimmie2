---
kind: primary
routes:
  web: Web
steps:
- text: The User enters the new password twice on their profile
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::user-profile
- text: The Product sets the Account's password and keeps the member signed in
  kind: product
  actor: user
  entities:
  - entity: account
    effect: changes
    facts: [Password]
  contexts:
    web:
      place: web::signed-in::user-profile
---

# Change own password

## Trigger

A member wants a new password.

## Outcome

The account has the new password and the member stays signed in.
