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

# Delete comment

An admin deletes a comment from a post.
