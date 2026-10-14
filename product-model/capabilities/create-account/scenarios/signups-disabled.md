---
kind: validation
routes:
  web: Web
steps:
- text: Anonymous opens Create Account
  kind: actor
  actor: anonymous
  entities:
  - entity: account
    effect: reads
    facts: []
  contexts:
    web:
      place: web::visitor::create-account
- text: The board does not allow new signups
  kind: condition
  entities:
  - entity: board
    effect: reads
    facts: [Allow new signups]
  contexts:
    web:
      place: web::visitor::create-account
- text: The Product shows that signups are disabled
  kind: product
  actor: anonymous
  entities: []
  contexts:
    web:
      place: web::visitor::create-account
---

# Signups disabled

## Trigger

A visitor opens sign-up while the board does not allow new signups.

## Outcome

No account is created and the visitor sees the board's message that signups are disabled.
