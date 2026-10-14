---
domain: account
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/user_config_editor/main.php#UserConfigEditor
- kind: code
  role: implementation
  target: ext/rating/config.php
---

# Change user options

A member chooses which ratings they see by default when browsing, among those their class may see. User options exist while the board runs post ratings.
