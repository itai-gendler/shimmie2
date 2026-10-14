---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Log Out
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in
- text: The Product ends the session and opens the front page
  kind: product
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in
---

# Log out

## Trigger

A member chooses Log Out.

## Outcome

The member's session ends and the front page opens for them as a visitor.
