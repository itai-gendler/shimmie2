---
kind: edge
routes:
  web: Web
steps:
- text: Anonymous enters a username and the password twice
  kind: actor
  actor: anonymous
  entities: []
  contexts:
    web:
      place: web::visitor::create-account
- text: No Account on the board is in the Admin class
  kind: condition
  entities:
  - entity: account
    effect: reads
    facts: [Class]
  - entity: admin
    effect: reads
    facts: []
  - entity: board
    effect: reads
    facts: []
  contexts:
    web:
      place: web::visitor::create-account
- text: The Product creates the Account in the Admin class and signs the person in
  kind: product
  actor: anonymous
  entities:
  - entity: account
    effect: creates
    facts: [Name, Password, Email, Class, Joined]
  - entity: admin
    effect: reads
    facts: []
  contexts:
    web:
      place: web::visitor::create-account
---

# First account becomes Admin

## Trigger

A visitor signs up on a board that has no Admin yet, such as a new installation.

## Outcome

The new account is in the Admin class.
