---
kind: person
acts: external
relations:
- entity: account
  verb: has
  cardinality: one-to-one
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
- kind: code
  role: implementation
  target: core/User/README.md
---

# Admin

A signed-in member in the shipped Admin class, which holds every permission.
Admins moderate posts, comments and accounts, configure the board, enable
extensions and manage user classes.
