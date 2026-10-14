---
kind: primary
routes:
  web: Web
steps:
- text: The Admin chooses Approve on a pending post
  kind: actor
  actor: admin
  entities:
  - entity: post
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::post
- text: The Product approves the Post and records who approved it
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
      place: web::signed-in::post
---

# Approve a post

## Trigger

An admin reviews a pending post.

## Outcome

The post is approved, credited to the approving admin, and listed for everyone.
