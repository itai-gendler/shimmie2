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

# Add tags to post

A member puts tags on a post; tags the board has not seen before come into being.
