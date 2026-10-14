---
kind: primary
routes:
  web: Web
steps:
- text: The User opens the list of posts they marked
  kind: actor
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post-list
- text: The Product lists the Posts the member has a Favorite on
  kind: product
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: [File, Tags]
  - entity: favorite
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post-list
---

# Browse my favorites

## Trigger

A member opens My Favorites.

## Outcome

The member sees the posts they marked as favorites.
