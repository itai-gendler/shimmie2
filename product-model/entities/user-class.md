---
domain: permission-manager
references:
- kind: code
  role: implementation
  target: core/User/UserClass.php
- kind: code
  role: implementation
  target: ext/perm_manager/main.php#PermManager
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
---

# User class

A named set of permissions that every account in the class holds, such as
Anonymous, User or Admin. Classes form a tree: a class without its own setting
for a permission takes it from its parent. The board ships the Anonymous, User
and Admin classes; operators may add classes in a configuration file, and
while the board runs Custom user classes admins create and change classes in
the Permission Manager.

## Information kept

- **Name** — the class name
- **Parent class** — the class it inherits permissions from
- **Description** — what the class is for
- **Permissions** — each permission the class grants or denies itself, the rest inherited
- **Member count** — how many accounts are in the class

## States

### Built-in

A class shipped with the board or defined in the operator's configuration
file, unchanged.

### Customized

A built-in class whose settings an admin has copied into the board to change
them.

### Custom

A class an admin created in the Permission Manager.
