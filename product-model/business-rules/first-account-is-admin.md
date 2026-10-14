---
appliesTo:
- type: capability
  id: create-account
- type: entity
  id: account
  effect: creates
references:
- kind: code
  role: implementation
  target: ext/user/main.php#UserPage
---

# The first account on a board without an Admin is an Admin

When an account is created while no account is in the Admin class, the new account goes into the Admin class instead of User.

## Rationale

A new installation has no one who could configure it; the first person to sign up becomes its Admin.
