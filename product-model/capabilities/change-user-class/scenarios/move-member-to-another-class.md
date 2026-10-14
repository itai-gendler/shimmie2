---
kind: primary
routes:
  web: Web
steps:
- text: The Admin picks a class on the member's profile
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::signed-in::user-profile
- text: The Product sets the Account's class
  kind: product
  actor: admin
  entities:
  - entity: account
    effect: changes
    facts: [Class]
  contexts:
    web:
      place: web::signed-in::user-profile
---

# Move a member to another class

## Trigger

An admin promotes, restricts or demotes a member.

## Outcome

The member holds the permissions of the new class from their next page on.
