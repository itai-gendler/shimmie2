---
appliesTo:
- type: entity
  id: tag
  effect: creates
- type: entity
  id: post
  effect: changes
  facts: [Tags]
references:
- kind: code
  role: implementation
  target: core/ImageBoard/Post.php#set_tags
- kind: code
  role: implementation
  target: core/ImageBoard/Tag.php#explode
---

# A tag has no spaces, never starts with a minus, never contains * and is at most 255 characters

Tags are single words; a leading minus means exclusion and * is a wildcard in searches, so neither can start or appear in a tag.
