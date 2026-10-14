---
domain: account
relations:
- entity: post
  verb: uploads
  cardinality: one-to-many
- entity: comment
  verb: writes
  cardinality: one-to-many
- entity: favorite
  verb: marks
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: core/User/User.php
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
- kind: code
  role: implementation
  target: ext/user_config_editor/main.php#UserConfigEditor
---

# Account

A person's account on the board, whatever their user class. Every post,
comment and favorite belongs to an account.

## Information kept

- **Name** — the username, made of letters, numbers, dashes and underscores, unique on the board
- **Email** — an optional email address
- **Password** — the secret the person signs in with
- **Class** — the user class that decides what the account may do
- **Joined** — when the account was created
- **Last active** — the last day the person used the board while signed in
- **Default ratings** — which post ratings the person sees by default when browsing, among those their class may see
