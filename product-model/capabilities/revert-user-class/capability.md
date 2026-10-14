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

# Revert user class

An admin discards the board's changes to a built-in class, returning it to its shipped or configured settings.
