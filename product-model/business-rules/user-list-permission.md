---
appliesTo:
- type: entity
  id: account
  effect: reads
  contexts:
  - place: web::board-admin::user-list
permits:
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
---

# Only admins read the user list

The User List, with every account's email and last activity, is open to classes that may edit other users' passwords, which by default is the Admin class.
