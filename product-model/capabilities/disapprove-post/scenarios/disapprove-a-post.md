---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Disapprove on an approved post
  kind: actor
  actor: admin
  entities:
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product returns the Post to the approval queue
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
      place: web::signed-in::post
---

# Disapprove a post

## Trigger

An admin decides an approved post needs review again.

## Outcome

The post is pending approval and hidden from everyone but its uploader and approvers.
