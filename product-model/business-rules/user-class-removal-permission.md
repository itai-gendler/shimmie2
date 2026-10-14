---
appliesTo:
- type: entity
  id: user-class
  effect: removes
permits:
- actors:
  - admin
  when:
  - entity: board
    fact: Custom user classes enabled
    is: true
- configuredBy: user-class
  when:
  - entity: board
    fact: Custom user classes enabled
    is: true
references:
- kind: code
  role: implementation
  target: ext/perm_manager/main.php#PermManager
---

# Only admins delete user classes

Managing user classes needs Manage user permissions, held by the Admin class by default, and is possible while the board runs Custom user classes.
