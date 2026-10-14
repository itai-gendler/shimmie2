---
entities:
- entity: comment
  shows: [Text, Posted, Edited]
- entity: post
  shows: [File, Tags]
entryPoints:
- web: /comment/list
references:
- kind: code
  role: implementation
  target: ext/comment/main.php#CommentList
- kind: code
  role: implementation
  target: ext/comment/theme.php
---

# Comments

Posts with recent comments, each post with its comment thread.
