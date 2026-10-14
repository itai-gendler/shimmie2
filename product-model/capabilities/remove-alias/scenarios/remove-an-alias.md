---
kind: primary
routes:
  web: Web
steps:
- text: The Admin deletes an alias from the list
  kind: actor
  actor: admin
  entities:
  - entity: alias
    effect: reads
    facts: []
  contexts:
    web:
      place: web::signed-in::aliases
- text: The Product removes the Alias
  kind: product
  actor: admin
  entities:
  - entity: alias
    effect: removes
  contexts:
    web:
      place: web::signed-in::aliases
---

# Remove an alias

## Trigger

An alias turns out to be wrong.

## Outcome

The old tag is no longer replaced; posts already retagged keep their tags.
