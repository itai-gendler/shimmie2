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

# Delete user

An admin deletes a member's account, choosing whether their posts and comments go with it.
