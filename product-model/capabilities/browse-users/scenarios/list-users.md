---
kind: primary
routes:
  web: Web
steps:
- text: The Admin opens the User List and filters it
  kind: actor
  actor: admin
  entities:
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::board-admin::user-list
- text: The Product lists matching Accounts
  kind: product
  actor: admin
  entities:
  - entity: account
    effect: reads
    facts: [Name, Email, Class, Joined, Last active]
  contexts:
    web:
      place: web::board-admin::user-list
---

# List users

## Trigger

An admin looks for an account.

## Outcome

The admin sees matching accounts with links to their profiles and posts.
