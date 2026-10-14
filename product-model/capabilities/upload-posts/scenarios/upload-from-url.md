---
kind: primary
routes:
  web: Web
steps:
- text: The board allows uploading from a URL
  kind: condition
  entities:
  - entity: board
    effect: reads
    facts: [Transload]
  contexts:
    web:
      place: web::signed-in::upload
- text: The User enters the file's URL with tags
  kind: actor
  actor: user
  entities:
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::upload
- text: The Product fetches the file and creates a Post from it with the URL as source
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
---

# Upload from a URL

## Trigger

A member wants to post a file that is online, on a board that allows transloading.

## Outcome

The fetched file is a new post whose source is the URL.

## Edge cases

- A URL that cannot be fetched is reported for that slot only.
