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
---

# User

A signed-in member of the board in the shipped User class. By default a User
uploads posts, edits the tags, source and rating of posts, marks favorites,
comments, and changes their own account.
