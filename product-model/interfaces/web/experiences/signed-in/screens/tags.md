---
entities:
- entity: tag
  shows: [Name, Post count]
entryPoints:
- web: /tags/map
references:
- kind: code
  role: implementation
  target: ext/tag_map/main.php#TagMap
- kind: code
  role: implementation
  target: ext/tag_map/theme.php
---

# Tags

Every tag in use, as a map sized by use, alphabetically or by popularity.
