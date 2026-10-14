---
appliesTo:
- type: entity
  id: post
  effect: changes
  facts: [Uploader]
permits:
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/post_owner/main.php#PostOwner
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
---

# Only admins change a post's uploader

Crediting a post to another account needs Edit post owner, held by the Admin class by default.
