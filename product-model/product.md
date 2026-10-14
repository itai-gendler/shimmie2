---
id: shimmie2
summary: 'A tag-based community image gallery (a booru): people upload posts, tag them, rate them, favorite them and comment on them, while admins moderate and configure the board.'
category: media-gallery
tags:
- image-gallery
- booru
- tagging
- community
authors:
- name: Shish
  url: https://github.com/shish
license: GPL-2.0-or-later
languages:
- en
limitations:
- A post holds exactly one file, and a file whose content is already on the board is never uploaded as a second post.
- Deleting a post removes it, its file, its comments and its favorites for good.
- 'Every post carries one rating from a fixed set: Safe, Questionable, Explicit or Unrated.'
- Features beyond the core gallery, such as the approval queue, ratings, favorites and custom user classes, are extensions an admin enables per board.
- What each class of user may do is decided by its user class, never per person.
---

# Shimmie

Shimmie is a tag-based image gallery that a community runs as its own board.
People browse and search posts by their tags, upload new files, tag and rate
them, mark favorites and comment. Admins keep the board in order: they approve
uploads when the board uses an approval queue, lock posts, merge tags with
aliases, and decide through user classes what each kind of user may do. Each
board is configured by its own admins, including which optional extensions it
runs.

## Intent

The project describes itself as "a tag-based image gallery". Its extensions
add the moderation and metadata a busy community needs: "an approval step to
the upload/import process", ratings so users can "rate images safe,
questionable or explicit", favorites ("a favorite this image button"), and
"point & click permission management" for user classes, which "form a tree,
where each class will inherit permissions from its parent".
