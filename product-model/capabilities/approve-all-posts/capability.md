---
domain: board-admin
availability:
- place: web::board-admin
references:
- kind: code
  role: implementation
  target: ext/approval/main.php#Approval
- kind: code
  role: implementation
  target: ext/approval/theme.php
---

# Approve all posts

An admin approves every post waiting in the approval queue at once.
