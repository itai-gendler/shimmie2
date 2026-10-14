---
domain: posts
availability:
- place: web::visitor
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/index/main.php#Index
- kind: code
  role: implementation
  target: core/Search/Search.php
- kind: code
  role: implementation
  target: ext/approval/main.php#Approval
- kind: code
  role: implementation
  target: ext/rating/main.php#Ratings
- kind: code
  role: implementation
  target: ext/favorites/main.php#Favorites
---

# Browse posts

Anyone lists the board's posts, newest first, and narrows them with a search of tags and filters such as rating, uploader, favorites or the approval queue.
