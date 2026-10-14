---
appliesTo:
- type: entity
  id: comment
  effect: changes
  facts: [Text, Edited]
permits:
- related:
  - verb: writes
    entity: account
  - verb: has
    entity: admin
references:
- kind: code
  role: implementation
  target: ext/comment/main.php#CommentList
---

# Only a comment's author edits it, and only with the Edit permission

Editing a comment needs the comment Edit permission, held by the Admin class by default, and even then only the comment's own author changes it.
