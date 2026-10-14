---
domain: account
availability:
- place: web::visitor
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
- kind: code
  role: implementation
  target: ext/user/theme.php
---

# Create account

A visitor signs up for an account on the board and is signed in to it. The very first account on a board becomes its Admin.
