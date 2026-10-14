---
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/upload/main.php#Upload
- kind: code
  role: implementation
  target: core/Extension/DataHandlerExtension.php#DataHandlerExtension
- kind: code
  role: implementation
  target: ext/upload/theme.php
- kind: code
  role: implementation
  target: ext/post_tags/main.php#PostTags
- kind: code
  role: implementation
  target: ext/approval/main.php#Approval
---

# Upload posts

A member uploads one or more files, or files from URLs, each becoming a post with the tags, source and rating given with it.
