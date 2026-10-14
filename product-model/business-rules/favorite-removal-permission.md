---
appliesTo:
- type: entity
  id: favorite
  effect: removes
permits:
- related:
  - verb: marks
    entity: account
  - verb: has
    entity: user
  when:
  - entity: board
    fact: Favorites enabled
    is: true
- related:
  - verb: marks
    entity: account
  - verb: has
    entity: admin
  when:
  - entity: board
    fact: Favorites enabled
    is: true
references:
- kind: code
  role: implementation
  target: ext/favorites/main.php#Favorites
---

# Members remove only their own favorites

A member removes only favorites of their own account, and only while the board runs favorites.
