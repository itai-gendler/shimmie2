---
appliesTo:
- type: capability
  id: add-comment
- type: entity
  id: comment
  effect: creates
references:
- kind: code
  role: implementation
  target: ext/comment/main.php#CommentList
---

# Members cannot flood or repeat comments

Unless their class may bypass content checks, a member's address may post at most the board's comment limit within its window, and a comment identical to one already on the post is refused.
