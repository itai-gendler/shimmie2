---
entities:
- entity: account
  shows: [Name, Email, Class, Joined, Last active]
entryPoints:
- web: /user_admin/list
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserTable
---

# User List

Every account, with its class, join date and last activity.
