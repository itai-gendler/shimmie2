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

# Delete user class

An admin deletes a custom class nobody belongs to.
