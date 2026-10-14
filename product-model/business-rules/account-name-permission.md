---
appliesTo:
- type: entity
  id: account
  effect: changes
  facts: [Name]
permits:
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
---

# Only admins rename accounts

Renaming an account needs Edit other users' names, which only the Admin class holds by default; members cannot rename themselves.
