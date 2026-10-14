---
domain: account
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
---

# Change email

A member changes the email address of their own account; an admin changes another member's.
