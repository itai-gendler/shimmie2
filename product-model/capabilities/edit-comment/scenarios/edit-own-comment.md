---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Edit on their comment, changes the text and saves
  kind: actor
  actor: admin
  entities:
  - entity: comment
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product replaces the Comment's text and marks it edited
  kind: product
  actor: admin
  entities:
  - entity: comment
    effect: changes
    facts: [Text, Edited]
  contexts:
    web:
      place: web::signed-in::post
---

# Edit own comment

## Trigger

An admin notices a mistake in their own comment.

## Outcome

The comment shows the new text and is marked edited.
