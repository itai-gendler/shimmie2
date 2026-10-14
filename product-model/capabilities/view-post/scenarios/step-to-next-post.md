---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Next on a post opened from a search
  kind: actor
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product opens the next Post matching the same search
  kind: product
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: [File, Tags]
  contexts:
    web:
      place: web::signed-in::post
---

# Step to the next post

## Trigger

A member reading posts from a search wants the next one.

## Outcome

The next post of the same search opens.

## Edge cases

- At the end of the search the Product reports there are no more posts.
