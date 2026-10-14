---
kind: primary
routes:
  web: Web
steps:
- text: The User searches for tags, excluding some with a minus and using wildcards
  kind: actor
  actor: user
  entities:
  - entity: tag
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post-list
- text: The Product resolves aliases and lists the Posts that match, within the member's default ratings
  kind: product
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: [File, Tags, Rating]
  - entity: tag
    effect: reads
    facts: [Name, Post count]
  - entity: account
    effect: reads
    facts: [Default ratings]
  - entity: alias
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post-list
---

# Search by tags

## Trigger

A member looks for posts about a subject.

## Outcome

The member sees the posts carrying every searched tag and none of the excluded ones, with related tags.

## Edge cases

- A search with exactly one result opens that post directly.
- Filters such as user=, favorited_by=, rating=, source= and posted< combine with tags.
