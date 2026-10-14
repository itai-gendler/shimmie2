---
appliesTo:
- type: entity
  id: alias
  effect: removes
permits:
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/alias_editor/main.php#AliasEditor
---

# Only admins remove aliases

Removing an alias needs the alias Admin permission, held by the Admin class by default.
