---
appliesTo:
- type: capability
  id: upload-posts
- type: entity
  id: post
  effect: creates
references:
- kind: code
  role: implementation
  target: ext/upload/main.php#Upload
---

# Uploads respect the board's file size limit and free disk space

A file larger than the board's maximum size per file, an empty or corrupt file, or a file of a type no handler supports is refused, and no uploads are taken while the board's disk is nearly full.
