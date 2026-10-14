---
domain: posts
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/post_source/main.php#PostSource
- kind: code
  role: implementation
  target: ext/view/main.php#ViewPost
---

# Change post source

A member records or corrects where a post's file came from.
