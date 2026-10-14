---
appliesTo:
- type: entity
  id: favorite
  effect: creates
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

# Members favorite posts for themselves while favorites run

A member marks favorites only for their own account, needs the favorites Edit permission, and only while the board runs favorites.
