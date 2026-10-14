---
appliesTo:
- type: entity
  id: post
  effect: changes
  facts: [Source]
permits:
- actors:
  - user
  when:
  - fact: Locked
    is: false
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/post_source/main.php#PostSource
---

# Members change the source of unlocked posts; admins of any post

Changing a post's source needs Edit post source. A locked post is changed only by classes that may lock posts.
