---
kind: validation
routes:
  web: Web
steps:
- text: Anonymous enters a name and password
  kind: actor
  actor: anonymous
  entities: []
  contexts:
    web:
      place: web::visitor::log-in
- text: No Account matches that name and password
  kind: condition
  entities:
  - entity: account
    effect: reads
    facts: [Name, Password]
  contexts:
    web:
      place: web::visitor::log-in
- text: The Product refuses the sign-in and keeps the visitor signed out
  kind: product
  actor: anonymous
  entities: []
  contexts:
    web:
      place: web::visitor::log-in
---

# Wrong name or password refused

## Trigger

A visitor enters a name or password that does not match an account.

## Outcome

The visitor stays signed out and is told the sign-in failed.
