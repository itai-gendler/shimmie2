---
appliesTo:
- type: entity
  id: post
  effect: removes
references:
- kind: code
  role: implementation
  target: ext/image/main.php#ImageIO
- kind: code
  role: implementation
  target: core/ImageBoard/Post.php#delete
---

# Deleting a post deletes its comments and favorites

A deleted post takes its file, its comments and its favorites with it, and its tags count one post fewer.
