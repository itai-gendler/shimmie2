---
domain: account
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
---

# Log out

A signed-in member ends their session on this browser.
