---
appliesTo:
- type: entity
  id: account
  effect: changes
  facts: [Password, Email]
permits:
- related:
  - verb: has
    entity: user
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
---

# A member changes their own password and email; admins change anyone's

A member changes the password and email of their own account. Changing another member's needs Edit other users' info; an account whose class is Protected, such as Admin, is changed only by its owner and by Admins.
