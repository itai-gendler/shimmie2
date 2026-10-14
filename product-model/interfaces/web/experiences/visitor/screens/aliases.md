---
entities:
- entity: alias
  shows: [Old tag, New tags]
- entity: tag
  shows: [Name]
entryPoints:
- web: /alias/list
references:
- kind: code
  role: implementation
  target: ext/alias_editor/main.php#AliasEditor
- kind: code
  role: implementation
  target: ext/alias_editor/theme.php
---

# Aliases

The list of tag aliases, which can be downloaded; admins add, remove and import aliases here.
