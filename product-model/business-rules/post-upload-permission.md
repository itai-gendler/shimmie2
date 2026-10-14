---
appliesTo:
- type: entity
  id: post
  effect: creates
permits:
- actors:
  - user
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/upload/main.php#Upload
---

# Members upload posts

Uploading needs Create post, which the User and Admin classes hold by default; Anonymous does not.
