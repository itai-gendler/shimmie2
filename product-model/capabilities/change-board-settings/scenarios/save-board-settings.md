---
kind: primary
routes:
  web: Web
steps:
- text: The Admin changes settings on Board Config and chooses Save Settings
  kind: actor
  actor: admin
  entities:
  - entity: board
    effect: reads
    facts: []
  contexts:
    web:
      place: web::board-admin::board-config
- text: The Product saves the Board's settings
  kind: product
  actor: admin
  entities:
  - entity: board
    effect: changes
    facts: [Site title, Front page, Theme, Allow new signups, Require email address, Terms and conditions, Login redirect, Max uploads, Max size per file, Upload collisions, Transload, Posts per page, Search
        result limit, Anonymous tag limit, Force tags to lowercase, Comment limit, Comment limit window, Ratings each class may see, After deleting a post]
  contexts:
    web:
      place: web::board-admin::board-config
---

# Save board settings

## Trigger

An admin wants the board to behave differently.

## Outcome

The board uses the new settings from the next page on.

## Edge cases

- Clearing a setting returns it to its default.
