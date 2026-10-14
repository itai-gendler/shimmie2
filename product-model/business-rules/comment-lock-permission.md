---
appliesTo:
- type: entity
  id: post
  effect: changes
  facts: [Comments locked]
permits:
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/comment/main.php#CommentList
---

# Only admins lock and unlock a post's comments

Locking a post's comments needs Edit Comment Lock, held by the Admin class by default.
