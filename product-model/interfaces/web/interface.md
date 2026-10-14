---
type: web
actors:
- anonymous
- user
- admin
entryPoints:
- web: /
- web: /post/list
references:
- kind: code
  role: implementation
  target: index.php
- kind: code
  role: implementation
  target: core/Page/Page.php
---

# Web

The board's website, where visitors browse, members contribute and admins run
the board.
