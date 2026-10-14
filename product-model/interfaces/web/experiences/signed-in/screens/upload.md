---
entities:
- entity: post
  collects: [File, Tags, Source, Rating]
- entity: tag
  shows: [Name, Post count]
- entity: board
  shows: [Max uploads, Max size per file]
entryPoints:
- web: /upload
references:
- kind: code
  role: implementation
  target: ext/upload/main.php#Upload
- kind: code
  role: implementation
  target: ext/upload/theme.php
---

# Upload

Where a member uploads one or more files, or links to files, with their tags, source and rating.
