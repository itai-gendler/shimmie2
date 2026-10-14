---
domain: posts
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/image/main.php#ImageIO
- kind: code
  role: implementation
  target: core/ImageBoard/Post.php#delete
---

# Delete post

An admin deletes a post, its file, tags, comments and favorites.
