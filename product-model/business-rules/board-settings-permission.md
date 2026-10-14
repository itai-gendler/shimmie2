---
appliesTo:
- type: entity
  id: board
  effect: changes
  facts: [Site title, Front page, Theme, Allow new signups, Require email address, Terms and conditions, Login redirect, Max uploads, Max size per file, Upload collisions, Transload, Posts per page, Search
      result limit, Anonymous tag limit, Force tags to lowercase, Comment limit, Comment limit window, Ratings each class may see, After deleting a post]
permits:
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/setup/main.php#Setup
---

# Only admins change board settings

Board Config needs the permission to modify web-level settings, held by the Admin class by default.
