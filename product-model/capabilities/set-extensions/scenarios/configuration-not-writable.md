---
kind: edge
routes:
  web: Web
steps:
- text: The Admin chooses Set Extensions
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::board-admin::extension-manager
- text: The board cannot write its extension list
  kind: condition
  entities:
  - entity: board
    effect: reads
    facts: [Enabled extensions]
  contexts:
    web:
      place: web::board-admin::extension-manager
- text: The Product reports that the configuration is not writable
  kind: product
  actor: admin
  entities: []
  contexts:
    web:
      place: web::board-admin::extension-manager
---

# Extension list cannot be saved

## Trigger

The board's configuration folder cannot be written on the server.

## Outcome

Nothing changes and the admin is told the configuration file is not writable.
