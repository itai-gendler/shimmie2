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

# Disapprove all posts

An admin sends every approved post back to the approval queue at once.
