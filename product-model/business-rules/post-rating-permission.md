---
appliesTo:
- type: entity
  id: post
  effect: changes
  facts: [Rating]
permits:
- actors:
  - user
  when:
  - fact: Locked
    is: false
  - entity: board
    fact: Ratings enabled
    is: true
- actors:
  - admin
  when:
  - entity: board
    fact: Ratings enabled
    is: true
- configuredBy: user-class
  when:
  - entity: board
    fact: Ratings enabled
    is: true
references:
- kind: code
  role: implementation
  target: ext/rating/main.php#Ratings
---

# Members rate unlocked posts while ratings run

Rating a post needs the Ratings Edit permission and the board running post ratings. A locked post is rated only by classes that may lock posts.
