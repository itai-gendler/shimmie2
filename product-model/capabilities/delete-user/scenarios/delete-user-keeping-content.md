---
kind: primary
routes:
  web: Web
steps:
- text: The Admin unlocks and confirms Delete User on the member's profile without ticking the delete boxes
  kind: actor
  actor: admin
  entities:
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::user-profile
- text: The Product credits the member's posts and comments to the anonymous account and deletes the Account
  kind: product
  actor: admin
  entities:
  - entity: post
    effect: changes
    facts: [Uploader]
  - entity: account
    effect: removes
  - entity: anonymous
    effect: reads
    facts: []
  - entity: comment
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::user-profile
---

# Delete a user and keep their content

## Trigger

An admin removes an account but wants its posts and comments to stay.

## Outcome

The account is gone; its posts and comments remain, credited to the anonymous account.
