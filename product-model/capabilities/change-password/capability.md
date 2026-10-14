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

# Change password

A member sets a new password for their own account; an admin sets one for another member.
