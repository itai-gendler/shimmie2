---
appliesTo:
- type: capability
  id: browse-posts
- type: entity
  id: post
  effect: reads
references:
- kind: code
  role: implementation
  target: ext/index/main.php#Index
- kind: code
  role: implementation
  target: core/Search/Search.php
---

# Searches are limited for classes without Big search

Members whose class lacks Big search see at most the board's search result limit for any search, and may combine at most the board's tag limit in one search. Signed-in Users and Admins hold Big search by default.
