---
appliesTo:
- type: capability
  id: upload-posts
- type: entity
  id: post
  effect: creates
references:
- kind: code
  role: implementation
  target: ext/approval/main.php#Approval
---

# Uploads wait for approval unless the uploader may bypass it

While the board runs the approval queue, a new post is pending approval unless its uploader's class holds Bypass Post Approval, which the Admin class does by default.
