---
appliesTo:
- type: entity
  id: board
  effect: changes
  facts: [Enabled extensions, Approval enabled, Ratings enabled, Favorites enabled, Custom user classes enabled]
permits:
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/ext_manager/main.php#ExtManager
---

# Only admins enable or disable extensions

The Extension Manager needs Enable or disable extensions, held by the Admin class by default.
