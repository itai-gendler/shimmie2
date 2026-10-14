---
domain: posts
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/post_lock/main.php#PostLock
---

# Unlock post

An admin lifts the lock on a post's information.
