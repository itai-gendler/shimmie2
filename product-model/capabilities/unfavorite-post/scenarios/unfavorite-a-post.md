---
kind: primary
routes:
  web: Web
steps:
- text: The User takes back their mark on the post
  kind: actor
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product removes the Favorite and lowers the Post's count
  kind: product
  actor: user
  entities:
  - entity: favorite
    effect: removes
  - entity: post
    effect: reads
    facts: [Favorite count]
  contexts:
    web:
      place: web::signed-in::post
---

# Un-favorite a post

## Trigger

A member no longer wants a post among their favorites.

## Outcome

The post leaves the member's favorites and its favorite count drops.
