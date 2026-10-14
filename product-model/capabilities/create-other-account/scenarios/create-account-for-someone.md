---
kind: primary
routes:
  web: Web
steps:
- text: The Admin enters a username, the password twice and optionally an email address
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::board-admin::board-admin
- text: The Product creates the Account in the User class without signing in to it
  kind: product
  actor: admin
  entities:
  - entity: account
    effect: creates
    facts: [Name, Password, Email, Class, Joined]
  - entity: user-class
    effect: reads
    facts: []
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::board-admin::board-admin
---

# Create an account for someone

## Trigger

An admin wants an account to exist for someone else.

## Outcome

The new account exists in the User class and the admin stays signed in as themselves.
