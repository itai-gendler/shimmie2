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

# Customize built-in class

An admin chooses Edit on a built-in class: the Product copies the class into the board so its settings can change, and opens it.
