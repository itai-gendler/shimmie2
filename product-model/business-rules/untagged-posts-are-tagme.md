---
appliesTo:
- type: entity
  id: post
  effect: creates
- type: entity
  id: post
  effect: changes
  facts: [Tags]
references:
- kind: code
  role: implementation
  target: core/ImageBoard/Tag.php#explode
---

# A post is never left without tags

A post given no tags, at upload or by clearing its tags, is tagged tagme.
