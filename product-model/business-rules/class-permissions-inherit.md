---
appliesTo:
- type: entity
  id: user-class
references:
- kind: code
  role: implementation
  target: core/User/UserClass.php
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
- kind: code
  role: implementation
  target: core/User/README.md
---

# A class takes every permission it does not set from its parent

A permission a class neither grants nor denies itself is decided by its parent class, up the tree. The Admin class holds every permission and the Base class at the root holds none; neither can be edited.
