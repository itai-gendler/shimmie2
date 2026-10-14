---
domain: board-admin
availability:
- place: web::board-admin
references:
- kind: code
  role: implementation
  target: ext/post_tags/main.php#PostTags
- kind: code
  role: implementation
  target: ext/post_tags/theme.php
---

# Replace tag

An admin replaces a tag, or a set of tags, with another across every post: a mass tag edit.
