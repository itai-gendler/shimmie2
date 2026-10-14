---
appliesTo:
- type: entity
  id: comment
  effect: removes
permits:
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/comment/main.php#CommentList
---

# Only admins delete comments

Deleting a comment needs the comment Delete permission, held by the Admin class by default.
