---
appliesTo:
- type: entity
  id: alias
- type: capability
  id: add-post-tags
- type: capability
  id: upload-posts
- type: capability
  id: browse-posts
references:
- kind: code
  role: implementation
  target: core/ImageBoard/Tag.php#explode
- kind: code
  role: implementation
  target: ext/alias_editor/main.php#AliasEditor
---

# An aliased tag is replaced by its new tags wherever it is used

When people tag a post or search, each tag with an alias is replaced by the alias's new tags, so the old tag never appears on a post.
