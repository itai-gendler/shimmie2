---
appliesTo:
- type: capability
  id: delete-user
- type: entity
  id: account
  effect: removes
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
---

# A deleted member's posts and comments stay unless deleted with them

Deleting an account credits its posts and comments to the anonymous account, unless the admin chooses to delete them with the account.
