---
domain: posts
relations:
- entity: comment
  verb: has
  cardinality: one-to-many
- entity: favorite
  verb: receives
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: core/ImageBoard/Post.php
- kind: code
  role: implementation
  target: ext/image/main.php#ImageIO
- kind: code
  role: implementation
  target: ext/approval/main.php#Approval
- kind: code
  role: implementation
  target: ext/approval/main.php#onDatabaseUpgrade
---

# Post

One uploaded file on the board with the information people attach to it.
While the board does not run the approval queue, every post is Approved.
Turning on the approval queue sends every post already on the board to
Pending approval, so they stay hidden until someone approves them.

## Information kept

- **File** — the uploaded media file and its thumbnail
- **File name** — the name the file was uploaded with
- **File type** — the kind of media the file holds
- **File size** — the size of the file
- **Dimensions** — the width and height of the media
- **Posted** — when the post was uploaded
- **Uploader** — the account credited with the post
- **Tags** — the tags describing the post
- **Source** — where the file came from, usually a link
- **Locked** — whether the post's information is locked against editing
- **Comments locked** — whether new comments on the post are closed
- **Rating** — Safe, Questionable, Explicit or Unrated
- **Favorite count** — how many accounts have the post among their favorites, following every favorite added or removed
- **Approved by** — the account that approved the post

## States

### Approved

The post is listed and shown to everyone whose class may see its rating.

### Pending approval

The post waits in the approval queue; only its uploader and those who approve
posts see it.
