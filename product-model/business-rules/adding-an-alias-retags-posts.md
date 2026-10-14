---
appliesTo:
- type: capability
  id: add-alias
- type: capability
  id: import-aliases
- type: entity
  id: alias
  effect: creates
references:
- kind: code
  role: implementation
  target: ext/post_tags/main.php#PostTags
- kind: code
  role: implementation
  target: ext/alias_editor/main.php#AliasEditor
---

# Adding an alias retags every post that has the old tag

When an alias is added, every post carrying the old tag is given the new tags instead.
