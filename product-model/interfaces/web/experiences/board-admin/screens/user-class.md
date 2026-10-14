---
entities:
- entity: user-class
  shows: [Name, Parent class, Description, Permissions]
  collects: [Parent class, Description, Permissions]
entryPoints:
- web: /user_class/{class}
references:
- kind: code
  role: implementation
  target: ext/perm_manager/main.php#PermManager
- kind: code
  role: implementation
  target: ext/perm_manager/theme.php
---

# User class

One class's parent and description, and each permission set to granted, denied or inherited.
