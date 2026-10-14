---
appliesTo:
- type: capability
  id: upload-posts
- type: entity
  id: post
  effect: creates
references:
- kind: code
  role: implementation
  target: core/Extension/DataHandlerExtension.php#DataHandlerExtension
---

# A file is on the board at most once

A file whose content is already a post never becomes a second post: depending on the board's upload collisions setting the upload is refused or its tags are added to the existing post.
