---
appliesTo:
- type: entity
  id: post
  effect: reads
permits:
- actors:
  - anonymous
  - user
  - admin
  when:
  - state: Approved
- related:
  - verb: uploads
    entity: account
  - verb: has
    entity: user
- actors:
  - admin
- configuredBy: user-class
references:
- kind: code
  role: implementation
  target: ext/approval/main.php#Approval
---

# A post pending approval is seen only by its uploader and those who approve posts

Everyone sees approved posts, within the ratings their class may see. A post pending approval is shown, listed and served only to its uploader and to classes that may approve posts.
