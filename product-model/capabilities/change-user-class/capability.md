---
domain: account
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
- kind: code
  role: implementation
  target: ext/user/theme.php
---

# Change user class

An admin moves a member's account into another user class, which changes everything that member may do.
