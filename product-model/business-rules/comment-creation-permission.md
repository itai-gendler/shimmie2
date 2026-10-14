---
appliesTo:
- type: entity
  id: comment
  effect: creates
permits:
- actors:
  - user
  when:
  - entity: post
    fact: Comments locked
    is: false
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/comment/main.php#CommentList
---

# Members comment on posts whose comments are open

Commenting needs Create comment, which the User and Admin classes hold by default. On a post with locked comments only classes that may bypass the comment lock comment.
