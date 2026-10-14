---
kind: primary
result: achieved
routes:
  web: Web
steps:
- text: The Admin chooses Delete after opening a search result
  kind: actor
  actor: admin
  capability: delete-post
  entities: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product deletes the Post and opens the next one of the search
  kind: product
  actor: admin
  capability: delete-post
  entities:
  - entity: post
    as: deleted-post
    effect: removes
    from: Approved
  - entity: board
    effect: reads
    facts: [After deleting a post]
  contexts:
    web:
      place: web::signed-in::post
- text: The Admin reviews the next Post
  kind: actor
  actor: admin
  capability: view-post
  entities:
  - entity: post
    as: next-post
    effect: reads
    facts: [File, Tags]
  contexts:
    web:
      place: web::signed-in::post
---

# Delete and review the next post

## Trigger

An admin works through a search of unwanted posts on a board that opens the next post after a deletion.

## Outcome

The next post of the search is open.
