---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Delete on the post and confirms
  kind: actor
  actor: admin
  entities:
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product deletes the Post, its Comments and Favorites and its file
  kind: product
  actor: admin
  entities:
  - entity: post
    effect: removes
    from: Approved
  - entity: comment
    effect: removes
    with: post
  - entity: favorite
    effect: removes
    with: post
  contexts:
    web:
      place: web::signed-in::post
- text: The Product follows the board's after-delete setting
  kind: condition
  entities:
  - entity: board
    effect: reads
    facts: [After deleting a post]
  contexts:
    web:
      place: web::signed-in::post
---

# Delete a post

## Trigger

An admin finds a post that does not belong on the board.

## Outcome

The post is gone with its comments and favorites, and the tags' counts drop.

## Decision points

### Where does the admin land?

What opens after the post is deleted?

- After deleting a post is "Return to list" → the page the admin came from
- After deleting a post is "Next post" → the next post of the same search
