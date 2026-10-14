---
kind: primary
routes:
  web: Web
steps:
- text: The User writes a comment and chooses Post Comment
  kind: actor
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: []
  - entity: comment
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product adds the Comment to the Post
  kind: product
  actor: user
  entities:
  - entity: comment
    effect: creates
    facts: [Text, Posted, Edited]
  - entity: post
    effect: reads
    facts: [Comments locked]
  contexts:
    web:
      place: web::signed-in::post
---

# Comment on a post

## Trigger

A member has something to say about a post.

## Outcome

The comment appears under the post.
