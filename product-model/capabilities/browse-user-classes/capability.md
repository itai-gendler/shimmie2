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
- kind: code
  role: implementation
  target: core/User/UserClass.php
---

# Browse user classes

An admin compares every user class: its parent, description, member count and what each permission resolves to.
