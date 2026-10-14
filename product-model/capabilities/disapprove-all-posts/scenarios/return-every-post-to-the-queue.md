---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Disapprove All in the approval tools
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::board-admin::board-admin
- text: The Product returns every approved Post to the approval queue
  kind: product
  actor: admin
  entities:
  - entity: post
    effect: changes
    from: Approved
    to: Pending approval
    facts: [Approved by]
  contexts:
    web:
      place: web::board-admin::board-admin
---

# Return every post to the queue

## Trigger

An admin starts using the approval queue and wants to review everything.

## Outcome

Every post is pending approval.
