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
  target: core/User/User.php
---

# Log in

A visitor signs in with their name and password and stays signed in on that browser.
