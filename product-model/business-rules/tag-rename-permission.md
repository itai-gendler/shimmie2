---
appliesTo:
- type: entity
  id: tag
  effect: changes
  facts: [Name]
permits:
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/post_tags/main.php#PostTags
---

# Only admins rename tags across the board

A mass tag edit needs Mass tag edit, held by the Admin class by default.
