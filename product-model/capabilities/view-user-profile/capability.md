---
domain: account
availability:
- place: web::visitor
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
- kind: code
  role: implementation
  target: ext/image/main.php#ImageIO
- kind: code
  role: implementation
  target: ext/comment/main.php#CommentList
- kind: code
  role: implementation
  target: ext/favorites/main.php#Favorites
---

# View user profile

Anyone reads a member's profile: when they joined, their class, how many posts, comments and favorites they have, and their latest comments.
