---
domain: comments
availability:
- place: web::visitor
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/comment/main.php#CommentList
- kind: code
  role: implementation
  target: ext/comment/theme.php
---

# Browse comments

Anyone reads the posts with the most recent comments, each with its comment thread.
