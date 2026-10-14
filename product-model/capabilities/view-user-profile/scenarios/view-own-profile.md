---
kind: primary
routes:
  web: Web
steps:
- text: The User opens My Profile
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::user-profile
- text: The Product shows the Account with its email address and the account operations
  kind: product
  actor: user
  entities:
  - entity: account
    effect: reads
    facts: [Name, Joined, Class, Email]
  contexts:
    web:
      place: web::signed-in::user-profile
---

# View own profile

## Trigger

A member opens My Profile.

## Outcome

The member sees their own profile with the operations they may perform on their account.
