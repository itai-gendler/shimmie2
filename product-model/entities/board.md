---
singleton: true
references:
- kind: code
  role: implementation
  target: ext/setup/main.php#Setup
- kind: code
  role: implementation
  target: ext/ext_manager/main.php#ExtManager
- kind: code
  role: implementation
  target: ext/user/config.php
- kind: code
  role: implementation
  target: ext/upload/config.php
- kind: code
  role: implementation
  target: ext/index/config.php
- kind: code
  role: implementation
  target: ext/comment/config.php
- kind: code
  role: implementation
  target: ext/rating/config.php
---

# Board

The board's own settings, kept once and changed by its admins.

## Information kept

- **Site title** — the board's name
- **Front page** — the page visitors land on
- **Theme** — the board's look
- **Allow new signups** — whether visitors may create accounts
- **Require email address** — whether signing up needs an email address
- **Terms and conditions** — text shown to people signing up
- **Login redirect** — whether signing in returns to the previous page or opens the profile
- **Max uploads** — how many files one upload form takes
- **Max size per file** — the largest file accepted
- **Upload collisions** — whether uploading a file already on the board is an error or merges its tags into the existing post
- **Transload** — whether and how posts may be uploaded from a URL
- **Posts per page** — how many posts a list page shows
- **Search result limit** — how many results a search shows to those without the Big search permission
- **Anonymous tag limit** — how many tags a search may combine for those without the Big search permission
- **Force tags to lowercase** — whether new tags are stored in lowercase
- **Comment limit** — how many comments one address may post within the window
- **Comment limit window** — the window, in minutes, for the comment limit
- **Ratings each class may see** — for each user class, which ratings its members may see
- **After deleting a post** — whether deleting a post returns to the list or opens the next post
- **Enabled extensions** — which optional extensions the board runs
- **Approval enabled** — whether the board runs the approval queue
- **Ratings enabled** — whether the board runs post ratings
- **Favorites enabled** — whether the board runs favorites
- **Custom user classes enabled** — whether admins manage user classes in the Permission Manager
