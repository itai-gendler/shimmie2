---
entities:
- entity: account
  collects: [Name, Password]
entryPoints:
- web: /user_admin/login
references:
- kind: code
  role: implementation
  target: ext/user/theme.php
---

# Log in

Where a visitor signs in with their name and password.
