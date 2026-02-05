---
layout: page
title: Event Guides
permalink: /events/
---

# Event & Mini-Game Strategy Guides

Master every event and mini-game in Last Z: Shooter Run with our comprehensive guides!

## Available Guides

{% assign event_posts = site.categories['events'] | sort: 'date' | reverse %}
{% for post in event_posts %}
### [{{ post.title }}]({{ post.url | relative_url }})
**{{ post.date | date: "%B %d, %Y" }}** - {{ post.excerpt | strip_html | truncatewords: 30 }}
{% endfor %}

{% if event_posts.size == 0 %}
*No event guides posted yet. Check back soon for detailed strategies!*
{% endif %}

---

## Quick Tips

- Always check event timers and plan your sessions accordingly
- Save your best gear for competitive events
- Coordinate with alliance members for team-based events
