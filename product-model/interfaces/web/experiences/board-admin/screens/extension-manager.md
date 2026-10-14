---
entities:
- entity: board
  shows: [Enabled extensions, Approval enabled, Ratings enabled, Favorites enabled, Custom user classes enabled]
  collects: [Enabled extensions, Approval enabled, Ratings enabled, Favorites enabled, Custom user classes enabled]
entryPoints:
- web: /ext_manager
references:
- kind: code
  role: implementation
  target: ext/ext_manager/main.php#ExtManager
- kind: code
  role: implementation
  target: ext/ext_manager/theme.php
---

# Extension Manager

Every optional extension with whether the board runs it.
