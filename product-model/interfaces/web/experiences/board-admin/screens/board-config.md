---
entities:
- entity: board
  shows: [Site title, Front page, Theme, Allow new signups, Require email address, Terms and conditions, Login redirect, Max uploads, Max size per file, Upload collisions, Transload, Posts per page, Search
      result limit, Anonymous tag limit, Force tags to lowercase, Comment limit, Comment limit window, Ratings each class may see, After deleting a post]
  collects: [Site title, Front page, Theme, Allow new signups, Require email address, Terms and conditions, Login redirect, Max uploads, Max size per file, Upload collisions, Transload, Posts per page,
    Search result limit, Anonymous tag limit, Force tags to lowercase, Comment limit, Comment limit window, Ratings each class may see, After deleting a post]
entryPoints:
- web: /setup
references:
- kind: code
  role: implementation
  target: ext/setup/main.php#Setup
- kind: code
  role: implementation
  target: ext/setup/theme.php
---

# Board Config

Every board setting, grouped by the extension it belongs to.
