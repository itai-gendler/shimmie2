---
domain: posts
availability:
- place: web::visitor
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/view/main.php#ViewPost
- kind: code
  role: implementation
  target: ext/image/main.php#ImageIO
- kind: code
  role: implementation
  target: ext/approval/main.php#Approval
- kind: code
  role: implementation
  target: ext/rating/main.php#Ratings
---

# View post

Anyone opens a post to see its media, information, tags, comments and who favorited it, and steps to the next or previous post of the same search.
