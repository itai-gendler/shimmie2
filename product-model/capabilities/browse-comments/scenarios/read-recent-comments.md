---
kind: primary
routes:
  web: Web
steps:
- text: Anonymous opens Comments
  kind: actor
  actor: anonymous
  entities:
  - entity: comment
    effect: reads
    facts: []
  contexts:
    web:
      place: web::visitor::comments
- text: The Product lists recently commented Posts with their Comments
  kind: product
  actor: anonymous
  entities:
  - entity: post
    effect: reads
    facts: [File, Tags]
  - entity: comment
    effect: reads
    facts: [Text, Posted, Edited]
  contexts:
    web:
      place: web::visitor::comments
---

# Read recent comments

## Trigger

A visitor wants to follow the board's discussion.

## Outcome

The visitor sees the recently commented posts they may see, newest discussion first.

## Edge cases

- Posts pending approval, or with a rating the visitor's class may not see, are left out.
