---
kind: primary
routes:
  web: Web
steps:
- text: Anonymous enters their name and password
  kind: actor
  actor: anonymous
  entities: []
  contexts:
    web:
      place: web::visitor::log-in
- text: The Product checks the name and password against the Account
  kind: product
  actor: anonymous
  entities:
  - entity: account
    effect: reads
    facts: [Name, Password]
  contexts:
    web:
      place: web::visitor::log-in
- text: The Product signs the visitor in
  kind: product
  actor: anonymous
  entities:
  - entity: account
    effect: reads
    facts: [Name]
  contexts:
    web:
      place: web::visitor::log-in
- text: The Product follows the board's login redirect
  kind: condition
  entities:
  - entity: board
    effect: reads
    facts: [Login redirect]
  contexts:
    web:
      place: web::visitor::log-in
---

# Log in with name and password

## Trigger

A visitor with an account wants to use the board as themselves.

## Outcome

The visitor is signed in and taken to their profile or back to the page they came from.

## Decision points

### Where does signing in lead?

Which page opens once the visitor is signed in?

- Login redirect is "Return to previous page" → the page the visitor was on before signing in
- Login redirect is "Go to profile" → the visitor's own profile
