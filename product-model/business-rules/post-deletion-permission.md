---
appliesTo:
- type: entity
  id: post
  effect: removes
permits:
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/image/main.php#ImageIO
---

# Only admins delete posts

Deleting any post needs Delete post; a class granted Delete own post deletes the posts it uploaded. By default only the Admin class deletes posts.
