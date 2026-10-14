---
kind: validation
routes:
  web: Web
steps:
- text: Anonymous enters a username, two passwords and an email address
  kind: actor
  actor: anonymous
  entities: []
  contexts:
    web:
      place: web::visitor::create-account
- text: The username is taken or malformed, the passwords differ, or a required email address is missing
  kind: condition
  entities:
  - entity: account
    effect: reads
    facts: [Name]
  - entity: board
    effect: reads
    facts: [Require email address]
  contexts:
    web:
      place: web::visitor::create-account
- text: The Product refuses to create the Account and explains why
  kind: product
  actor: anonymous
  entities:
  - entity: account
    effect: reads
    facts: []
  contexts:
    web:
      place: web::visitor::create-account
---

# Invalid sign-up refused

## Trigger

A visitor signs up with a username that is taken or malformed, passwords that differ, or no email address where one is required.

## Outcome

No account is created and the visitor is told what to fix.
