---
appliesTo:
- type: entity
  id: account
  effect: changes
  facts: [Default ratings]
permits:
- related:
  - verb: has
    entity: user
  when:
  - entity: board
    fact: Ratings enabled
    is: true
- actors:
  - admin
  when:
  - entity: board
    fact: Ratings enabled
    is: true
references:
- kind: code
  role: implementation
  target: ext/user_config_editor/main.php#UserConfigEditor
---

# A member changes their own options while ratings run

A member changes their own user options; changing another member's needs Change other users' settings. User options exist while the board runs post ratings.
