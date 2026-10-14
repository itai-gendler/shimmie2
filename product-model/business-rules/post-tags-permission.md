---
appliesTo:
- type: entity
  id: post
  effect: changes
  facts: [Tags]
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
  target: ext/post_tags/main.php#PostTags
- kind: code
  role: implementation
  target: ext/post_lock/main.php#PostLock
---

# Members change the tags of unlocked posts; admins of any post

Changing a post's tags needs Edit post tag. A locked post is changed only by classes that may lock posts.
