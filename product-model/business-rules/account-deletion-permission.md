---
appliesTo:
- type: entity
  id: account
  effect: removes
permits:
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
---

# Only admins delete accounts

Deleting an account needs Delete other users, which only the Admin class holds by default.
