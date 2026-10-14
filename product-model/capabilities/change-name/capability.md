---
domain: account
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
---

# Change name

An admin renames a member's account.
