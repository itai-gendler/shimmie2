---
appliesTo:
- type: entity
  id: post
  effect: changes
  facts: [Locked]
permits:
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/post_lock/main.php#PostLock
---

# Only admins lock and unlock posts

Locking and unlocking a post needs Edit post lock, held by the Admin class by default.
