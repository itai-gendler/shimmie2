---
kind: primary
routes:
  web: Web
steps:
- text: The User adds a new tag to the post and saves
  kind: actor
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: []
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product creates the Tag and puts it on the Post
  kind: product
  actor: user
  entities:
  - entity: post
    effect: changes
    facts: [Tags]
  - entity: tag
    effect: creates
    facts: [Name, Post count]
  contexts:
    web:
      place: web::signed-in::post
---

# Add a tag the board has not seen

## Trigger

A member tags a post with a word nobody has used yet.

## Outcome

The tag now exists with one post.

## Edge cases

- On a board that forces lowercase the new tag is stored in lowercase.
