---
domain: aliases
availability:
- place: web::signed-in
references:
- kind: code
  role: implementation
  target: ext/alias_editor/main.php#AliasEditor
- kind: code
  role: implementation
  target: ext/post_tags/main.php#PostTags
---

# Add alias

An admin makes one tag stand for one or more others; existing posts with the old tag are retagged.
