---
appliesTo:
- type: entity
  id: alias
  effect: creates
references:
- kind: code
  role: implementation
  target: ext/alias_editor/main.php#AliasEditor
---

# A tag has at most one alias and an alias never leads to another alias

An old tag can be aliased once, and a tag that is itself aliased cannot be another alias's new tag.
