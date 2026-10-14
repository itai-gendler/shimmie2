---
kind: primary
routes:
  web: Web
steps:
- text: The Admin opens Pending Approval
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::signed-in::post-list
- text: The Product lists the Posts pending approval
  kind: product
  actor: admin
  entities:
  - entity: post
    effect: reads
    facts: [File, Tags]
  contexts:
    web:
      place: web::signed-in::post-list
---

# Browse the approval queue

## Trigger

An admin opens Pending Approval.

## Outcome

The admin sees every post waiting for approval.

## Edge cases

- A member who cannot approve posts sees only their own posts in the queue.
