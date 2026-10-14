---
kind: primary
routes:
  web: Web
steps:
- text: The Admin ticks and clears extensions and chooses Set Extensions
  kind: actor
  actor: admin
  entities: []
  contexts:
    web:
      place: web::board-admin::extension-manager
- text: The Product saves the Board's enabled extensions
  kind: product
  actor: admin
  entities:
  - entity: board
    effect: changes
    facts: [Enabled extensions, Approval enabled, Ratings enabled, Favorites enabled, Custom user classes enabled]
  contexts:
    web:
      place: web::board-admin::extension-manager
---

# Enable and disable extensions

## Trigger

An admin wants the board to run the approval queue and stop running another extension.

## Outcome

The board runs exactly the ticked extensions plus the core ones.

## Edge cases

- Core extensions in the submission are ignored: they cannot be turned off.
