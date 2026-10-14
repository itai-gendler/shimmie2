---
availability:
- place: web::board-admin
references:
- kind: code
  role: implementation
  target: ext/ext_manager/main.php#ExtManager
- kind: code
  role: implementation
  target: ext/ext_manager/theme.php
- kind: code
  role: implementation
  target: core/Config/SysConfig.php#getExtraExtensions
---

# Set extensions

An admin chooses which optional extensions the board runs; core extensions always run.
