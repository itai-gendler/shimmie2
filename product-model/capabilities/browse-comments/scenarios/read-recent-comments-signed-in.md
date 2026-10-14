---
kind: primary
routes:
  web: Web
steps:
- text: The User opens Comments
  kind: actor
  actor: user
  entities:
  - entity: comment
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::comments
- text: The Product lists recently commented Posts with their Comments
  kind: product
  actor: user
  entities:
  - entity: post
    effect: reads
    facts: [File, Tags]
  - entity: comment
    effect: reads
    facts: [Text, Posted, Edited]
  contexts:
    web:
      place: web::signed-in::comments
---

# Read recent comments while signed in

## Trigger

A member checks the discussion.

## Outcome

The member sees recent comment threads with a box to reply on each post.
