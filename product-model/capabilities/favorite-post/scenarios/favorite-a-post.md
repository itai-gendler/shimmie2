---
kind: primary
routes:
  web: Web
steps:
- text: The User marks the post as one they like
  kind: actor
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product records the Favorite and counts it on the Post
  kind: product
  actor: user
  entities:
  - entity: favorite
    effect: creates
    facts: [Favorited at]
  - entity: post
    effect: reads
    facts: [Favorite count]
  contexts:
    web:
      place: web::signed-in::post
---

# Favorite a post

## Trigger

A member likes a post.

## Outcome

The post is among the member's favorites and its favorite count grows.
