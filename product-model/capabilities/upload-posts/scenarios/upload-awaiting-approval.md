---
kind: primary
routes:
  web: Web
steps:
- text: The board runs the approval queue
  kind: condition
  entities:
  - entity: board
    effect: reads
    facts: [Approval enabled]
  contexts:
    web:
      place: web::signed-in::upload
- text: The User picks a file and gives its tags
  kind: actor
  actor: user
  entities:
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::upload
- text: The Product creates the Post pending approval
  kind: product
  actor: user
  entities:
  - entity: post
    effect: creates
    to: Pending approval
    facts: [File, File name, File type, File size, Dimensions, Posted, Uploader, Tags, Source, Rating]
  contexts:
    web:
      place: web::signed-in::upload
---

# Upload awaiting approval

## Trigger

A member without the Bypass post approval permission uploads while the board runs the approval queue.

## Outcome

The new post is pending approval: the uploader sees it, everyone else only once it is approved.
