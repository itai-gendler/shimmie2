---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Approve All in the approval tools
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::board-admin::board-admin
- text: The Product approves every Post pending approval
  kind: product
  actor: admin
  entities:
  - entity: post
    effect: changes
    from: Pending approval
    to: Approved
    facts: [Approved by]
  contexts:
    web:
      place: web::board-admin::board-admin
---

# Approve the whole queue

## Trigger

An admin trusts everything in the queue.

## Outcome

Every pending post is approved and credited to the admin.
