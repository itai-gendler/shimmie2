---
domain: permission-manager
availability:
- place: web::board-admin
references:
- kind: code
  role: implementation
  target: ext/perm_manager/main.php#PermManager
- kind: code
  role: implementation
  target: ext/perm_manager/theme.php
---

# Create user class

An admin creates a new user class under a parent class, then sets its permissions. Classes are created while the board runs Custom user classes.
