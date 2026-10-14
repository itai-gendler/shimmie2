---
entities:
- entity: account
  collects: [Name, Password, Email]
- entity: board
  shows: [Terms and conditions]
entryPoints:
- web: /user_admin/create
references:
- kind: code
  role: implementation
  target: ext/user/theme.php
---

# Create account

Where a visitor signs up, after reading the board's terms and conditions.
