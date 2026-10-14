---
availability:
- place: web::visitor
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/tag_map/main.php#TagMap
- kind: code
  role: implementation
  target: ext/tag_map/theme.php
---

# Browse tags

Anyone lists the tags in use as a map, alphabetically or by popularity, and follows a tag to its posts.
