---
appliesTo:
- type: capability
  id: delete-user-class
- type: entity
  id: user-class
  effect: removes
references:
- kind: code
  role: implementation
  target: ext/perm_manager/theme.php
---

# Only a custom class nobody belongs to is deleted

A class with members cannot be deleted, and built-in classes are reverted rather than deleted.
