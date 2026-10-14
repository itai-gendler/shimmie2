---
kind: primary
routes:
  web: Web
steps:
- text: Anonymous opens a member's profile
  kind: actor
  actor: anonymous
  entities: []
  contexts:
    web:
      place: web::visitor::user-profile
- text: The Product shows the Account's join date, class, activity counts and recent Comments
  kind: product
  actor: anonymous
  entities:
  - entity: account
    effect: reads
    facts: [Name, Joined, Class]
  - entity: comment
    effect: reads
    facts: [Text, Posted]
  contexts:
    web:
      place: web::visitor::user-profile
---

# View a profile

## Trigger

A visitor follows a member's name.

## Outcome

The visitor sees the member's profile with links to their posts and favorites.

## Edge cases

- The anonymous account has no profile; asking for it shows that no such user exists.
