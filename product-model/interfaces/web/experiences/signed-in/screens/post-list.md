---
entities:
- entity: post
  shows: [File, Tags, Rating]
- entity: tag
  shows: [Name, Post count]
entryPoints:
- web: /post/list
references:
- kind: code
  role: implementation
  target: ext/index/main.php#Index
- kind: code
  role: implementation
  target: ext/index/theme.php
- kind: code
  role: implementation
  target: ext/tag_list/main.php
---

# Post list

The list of posts, newest first, narrowed by a search of tags and filters, with popular or related tags beside it.
