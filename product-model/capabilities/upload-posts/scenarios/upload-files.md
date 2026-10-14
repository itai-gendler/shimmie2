---
kind: primary
routes:
  web: Web
steps:
- text: The board accepts uploads
  kind: condition
  entities:
  - entity: board
    effect: reads
    facts: [Max uploads, Max size per file]
  contexts:
    web:
      place: web::signed-in::upload
- text: The User picks files and gives tags, a source and a rating for all or for each
  kind: actor
  actor: user
  entities:
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::upload
- text: The Product creates a Post for each supported file, crediting the uploader
  kind: product
  actor: user
  entities:
  - entity: post
    effect: creates
    to: Approved
    facts: [File, File name, File type, File size, Dimensions, Posted, Uploader, Tags, Source, Rating]
  contexts:
    web:
      place: web::signed-in::upload
- text: The Product puts each given Tag on the post, creating tags it has not seen
  kind: product
  actor: user
  entities:
  - entity: tag
    effect: creates
    facts: [Name, Post count]
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::upload
- text: The Product shows which files became posts
  kind: product
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: [File name]
  contexts:
    web:
      place: web::signed-in::upload
---

# Upload files

## Trigger

A member has files to share.

## Outcome

Each file is a new post with its tags, and the member sees the result of every file.

## Edge cases

- A file given without tags is tagged tagme.
- Per-file tags are added to the tags given for all files.
