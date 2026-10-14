---
kind: primary
routes:
  web: Web
steps:
- text: Anonymous opens a post
  kind: actor
  actor: anonymous
  entities:
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::visitor::post
- text: The Product shows the Post with its Tags and Comments
  kind: product
  actor: anonymous
  entities:
  - entity: post
    effect: reads
    facts: [File, File name, File type, File size, Dimensions, Posted, Uploader, Tags, Source, Rating, Favorite count]
  - entity: tag
    effect: reads
    facts: [Name, Post count]
  - entity: comment
    effect: reads
    facts: [Text, Posted, Edited]
  contexts:
    web:
      place: web::visitor::post
---

# View a post

## Trigger

A visitor opens a post from the list.

## Outcome

The visitor sees the post's media and everything known about it.
