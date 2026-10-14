---
kind: primary
routes:
  web: Web
steps:
- text: The User picks a rating on the post and saves
  kind: actor
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product sets the Post's rating
  kind: product
  actor: user
  entities:
  - entity: post
    effect: changes
    facts: [Rating]
  contexts:
    web:
      place: web::signed-in::post
---

# Rate a post

## Trigger

A member sees a post with a missing or wrong rating.

## Outcome

The post has the new rating, which decides who sees it.

## Edge cases

- A rating=… metatag in the tag list sets the rating the same way.
