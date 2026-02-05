---
layout: default
title: Canyon Clash
permalink: /canyon-clash/
---

# Canyon Clash Weekly Strategies

Stay ahead in Canyon Clash with our weekly updated strategies and tactics!

## This Week's Strategy

{% assign clash_posts = site.categories.canyon-clash | sort: 'date' | reverse %}
{% assign latest_clash = clash_posts | first %}

{% if latest_clash %}
### [{{ latest_clash.title }}]({{ latest_clash.url | relative_url }})
**{{ latest_clash.date | date: "%B %d, %Y" }}**

{{ latest_clash.excerpt }}

[Read Full Strategy]({{ latest_clash.url | relative_url }})
{% else %}
*No Canyon Clash strategies posted yet. Check back soon!*
{% endif %}

---

## Previous Weeks

{% for post in clash_posts offset:1 %}
- [{{ post.title }}]({{ post.url | relative_url }}) - *{{ post.date | date: "%B %d, %Y" }}*
{% endfor %}

---

## General Canyon Clash Tips

- Scout the battlefield layout each week - it changes!
- Coordinate attacks with your alliance
- Balance offense and defense - don't leave your base unprotected
- Save powerful abilities for critical moments
