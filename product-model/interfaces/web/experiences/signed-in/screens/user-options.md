---
entities:
- entity: account
  shows: [Default ratings]
  collects: [Default ratings]
entryPoints:
- web: /user_config
references:
- kind: code
  role: implementation
  target: ext/user_config_editor/main.php#UserConfigEditor
---

# User options

A member's own preferences, such as the ratings they see by default.
