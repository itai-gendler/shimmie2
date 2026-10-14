---
appliesTo:
- type: entity
  id: alias
  effect: creates
permits:
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/alias_editor/main.php#AliasEditor
---

# Only admins add aliases

Adding or importing aliases needs the alias Admin permission, held by the Admin class by default.
