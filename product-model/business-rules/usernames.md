---
appliesTo:
- type: entity
  id: account
  effect: creates
- type: entity
  id: account
  effect: changes
  facts: [Name]
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
---

# Usernames are unique and use letters, numbers, dashes and underscores

A username is at least one character of letters, numbers, dash and underscore, and no two accounts share one.
