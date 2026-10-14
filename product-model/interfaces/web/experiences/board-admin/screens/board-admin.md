---
entities:
- entity: account
  collects: [Name, Password, Email]
- entity: tag
  collects: [Name]
entryPoints:
- web: /admin
references:
- kind: code
  role: implementation
  target: ext/admin/main.php#AdminPage
- kind: code
  role: implementation
  target: ext/admin/theme.php
- kind: code
  role: implementation
  target: ext/post_tags/theme.php
- kind: code
  role: implementation
  target: ext/approval/theme.php
---

# Board Admin

Admin power tools: creating accounts for others, mass tag edits, and approving or disapproving every post at once.
