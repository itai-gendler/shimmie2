---
domain: board-admin
availability:
- place: web::board-admin
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
- kind: code
  role: implementation
  target: ext/user/theme.php
---

# Create an account for someone

An admin creates an account for another person from Board Admin, even while signups are closed and without an email address.
