---
domain: posts
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/post_lock/main.php#PostLock
---

# Lock post

An admin locks a post's information so only those who may lock posts can edit it.
