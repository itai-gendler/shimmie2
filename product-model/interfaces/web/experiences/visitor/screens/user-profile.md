---
entities:
- entity: account
  shows: [Name, Joined, Class]
- entity: comment
  shows: [Text, Posted]
entryPoints:
- web: /user/{name}
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
- kind: code
  role: implementation
  target: ext/user/theme.php
---

# User profile

A member's page: when they joined, their class, how many posts, comments and favorites they have, and their recent comments; the owner and admins also find the account's operations here.
