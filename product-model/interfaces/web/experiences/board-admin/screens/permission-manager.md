---
entities:
- entity: user-class
  shows: [Name, Parent class, Description, Permissions, Member count]
  collects: [Name, Parent class, Description]
entryPoints:
- web: /perm_manager
references:
- kind: code
  role: implementation
  target: ext/perm_manager/main.php#PermManager
- kind: code
  role: implementation
  target: ext/perm_manager/theme.php
---

# Permission Manager

Every user class with its parent, description and members, a comparison of their permissions, and the controls to create, edit, revert or delete classes.
