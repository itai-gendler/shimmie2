---
domain: posts
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/approval/main.php#Approval
---

# Approve post

An admin approves a post waiting in the approval queue so everyone may see it. Approval exists while the board runs the approval queue.
