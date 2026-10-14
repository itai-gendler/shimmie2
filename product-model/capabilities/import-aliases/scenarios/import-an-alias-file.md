---
kind: primary
routes:
  web: Web
steps:
- text: The Admin uploads a CSV file of aliases
  kind: actor
  actor: admin
  entities:
  - entity: alias
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::aliases
- text: The Product adds an Alias for each line, retagging Posts
  kind: product
  actor: admin
  entities:
  - entity: alias
    effect: creates
    facts: [Old tag, New tags]
  - entity: post
    effect: changes
    facts: [Tags]
  contexts:
    web:
      place: web::signed-in::aliases
---

# Import an alias file

## Trigger

An admin brings aliases from another board.

## Outcome

Each line of the file is an alias, and posts are retagged as for a single alias.
