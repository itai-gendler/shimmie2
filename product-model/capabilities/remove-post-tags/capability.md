---
domain: posts
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/post_tags/main.php#PostTags
- kind: code
  role: implementation
  target: core/ImageBoard/Tag.php#explode
- kind: code
  role: implementation
  target: ext/view/main.php#ViewPost
- kind: code
  role: implementation
  target: ext/post_lock/main.php#PostLock
---

# Remove tags from post

A member takes tags off a post.
