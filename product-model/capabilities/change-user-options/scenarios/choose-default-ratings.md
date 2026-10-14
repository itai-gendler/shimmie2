---
kind: primary
routes:
  web: Web
steps:
- text: The User picks their default ratings and saves
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::user-options
- text: The Product saves the Account's default ratings
  kind: product
  actor: user
  entities:
  - entity: account
    effect: changes
    facts: [Default ratings]
  contexts:
    web:
      place: web::signed-in::user-options
---

# Choose default ratings

## Trigger

A member wants to stop seeing a rating by default.

## Outcome

Searches without a rating term show only the chosen ratings.
