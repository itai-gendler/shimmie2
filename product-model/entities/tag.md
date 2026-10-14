---
relations:
- entity: post
  verb: labels
  cardinality: many-to-many
references:
- kind: code
  role: implementation
  target: core/ImageBoard/Tag.php
- kind: code
  role: implementation
  target: ext/tag_map/main.php#TagMap
---

# Tag

A word that describes posts. A tag comes into being the first time it is put
on a post, and people find posts by searching for their tags.

## Information kept

- **Name** — the tag itself, without spaces
- **Post count** — how many posts carry the tag, following every change to posts' tags
