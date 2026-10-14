---
appliesTo:
- type: entity
  id: post
  effect: changes
  to: Approved
permits:
- actors:
  - admin
  when:
  - entity: board
    fact: Approval enabled
    is: true
- configuredBy: user-class
  when:
  - entity: board
    fact: Approval enabled
    is: true
references:
- kind: code
  role: implementation
  target: ext/approval/main.php#Approval
---

# Only approvers approve posts

Approving and disapproving posts needs Approve Posts, held by the Admin class by default, and exists while the board runs the approval queue.
