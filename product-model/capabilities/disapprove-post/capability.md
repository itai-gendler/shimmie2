---
domain: posts
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/approval/main.php#Approval
---

# Disapprove post

An admin sends an approved post back to the approval queue, hiding it again.
