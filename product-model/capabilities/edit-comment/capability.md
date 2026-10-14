---
domain: comments
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/comment/main.php#CommentList
- kind: code
  role: implementation
  target: ext/comment/theme.php
---

# Edit comment

The author of a comment changes its text, if their class may edit comments.
