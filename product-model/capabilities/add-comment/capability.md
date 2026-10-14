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

# Add comment

A member writes a comment on a post.
