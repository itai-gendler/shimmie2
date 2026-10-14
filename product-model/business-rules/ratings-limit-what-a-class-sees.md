---
appliesTo:
- type: entity
  id: post
  effect: reads
- type: capability
  id: browse-posts
references:
- kind: code
  role: implementation
  target: ext/rating/main.php#Ratings
---

# A class sees only the ratings the board allows it

Each user class may see only the ratings the board allows it. A post with any other rating is left out of lists and searches, opening it leads to the front page, and its file is refused. Within what their class may see, a member's default ratings decide what searches show unless a search names a rating. This holds while the board runs post ratings.
