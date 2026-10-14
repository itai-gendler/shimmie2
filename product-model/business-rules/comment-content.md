---
appliesTo:
- type: entity
  id: comment
  effect: creates
- type: entity
  id: comment
  effect: changes
  facts: [Text, Edited]
references:
- kind: code
  role: implementation
  target: ext/comment/main.php#CommentList
---

# A comment has text, at most 9000 characters, and is not mostly repetition

Empty comments, comments over 9000 characters and comments that compress more than tenfold are refused, as are comments sent from a form more than a few hours old.
