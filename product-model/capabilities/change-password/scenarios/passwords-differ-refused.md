---
kind: validation
routes:
  web: Web
steps:
- text: The User enters two different passwords
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::user-profile
- text: The Product refuses the change because the passwords don't match
  kind: product
  actor: user
  entities:
  - entity: account
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::user-profile
---

# Passwords that differ refused

## Trigger

A member types two different passwords.

## Outcome

The password is unchanged and the member is told the passwords don't match.
