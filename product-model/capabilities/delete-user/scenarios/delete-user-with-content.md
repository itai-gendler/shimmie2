---
kind: primary
routes:
  web: Web
steps:
- text: The Admin ticks Delete images and Delete comments and confirms Delete User
  kind: actor
  actor: admin
  entities:
  - entity: user
    effect: reads
    facts: []
  - entity: comment
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::user-profile
- text: The Product deletes the member's Posts and Comments and then the Account
  kind: product
  actor: admin
  entities:
  - entity: account
    effect: removes
  - entity: post
    effect: removes
    from: Approved
    with: account
  - entity: comment
    effect: removes
    with: account
  contexts:
    web:
      place: web::signed-in::user-profile
---

# Delete a user with their posts and comments

## Trigger

An admin removes a spammer together with everything they posted.

## Outcome

The account, its posts and its comments are gone.
