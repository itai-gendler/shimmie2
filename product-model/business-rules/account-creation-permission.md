---
appliesTo:
- type: entity
  id: account
  effect: creates
permits:
- actors:
  - anonymous
  when:
  - entity: board
    fact: Allow new signups
    is: true
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
---

# Visitors sign up only while signups are allowed; admins create accounts any time

Anonymous creates an account only while the board allows new signups. Admins, and any class granted Create other users, create accounts for others whatever that setting says. Every grant here is a permission of the user class, which the Permission Manager can change.
