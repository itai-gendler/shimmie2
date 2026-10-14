---
appliesTo:
- type: entity
  id: account
  effect: changes
  facts: [Class]
permits:
- actors:
  - admin
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
---

# Only admins change a member's class

Only members of the Admin class move an account into another class, whatever permissions other classes hold.
