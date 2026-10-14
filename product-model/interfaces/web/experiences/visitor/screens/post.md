---
entities:
- entity: post
  shows: [File, File name, File type, File size, Dimensions, Posted, Uploader, Tags, Source, Locked, Comments locked, Rating, Favorite count]
- entity: tag
  shows: [Name, Post count]
- entity: comment
  shows: [Text, Posted, Edited]
- entity: account
  shows: [Name]
entryPoints:
- web: /post/view/{id}
references:
- kind: code
  role: implementation
  target: ext/view/main.php#ViewPost
- kind: code
  role: implementation
  target: ext/view/theme.php
- kind: code
  role: implementation
  target: ext/comment/theme.php
---

# Post

One post: its media, its information and tags, who favorited it, its comments, and the controls the viewer may use on it.
