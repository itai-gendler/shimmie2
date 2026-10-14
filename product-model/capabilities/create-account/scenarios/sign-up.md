---
kind: primary
routes:
  web: Web
steps:
- text: The board allows new signups
  kind: condition
  entities:
  - entity: board
    effect: reads
    facts: [Allow new signups, Terms and conditions]
  contexts:
    web:
      place: web::visitor::create-account
- text: Anonymous enters a username, the password twice and an email address
  kind: actor
  actor: anonymous
  entities: []
  contexts:
    web:
      place: web::visitor::create-account
- text: The Product creates the Account in the User class
  kind: product
  actor: anonymous
  entities:
  - entity: account
    effect: creates
    facts: [Name, Password, Email, Class, Joined]
  - entity: user-class
    effect: reads
    facts: []
  - entity: user
    effect: reads
    facts: []
  contexts:
    web:
      place: web::visitor::create-account
- text: The Product signs the new member in and opens their profile
  kind: product
  actor: anonymous
  entities:
  - entity: account
    effect: reads
    facts: []
  contexts:
    web:
      place: web::visitor::user-profile
---

# Sign up

## Trigger

A visitor wants an account on a board that allows new signups.

## Outcome

The visitor has a new account in the User class, is signed in to it and sees their profile.

## Edge cases

- Without an email address the account is still created unless the board requires one.
- A CAPTCHA appears when the board runs a CAPTCHA extension.
