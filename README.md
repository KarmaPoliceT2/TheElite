# [t0p1]The Elite - Last Z: Shooter Run Strategy Hub

Official strategy and tips website for [t0p1]The Elite alliance in Last Z: Shooter Run.

## Site Structure

### Pages
- **Home** ([index.md](index.md)): Landing page with overview
- **Daily Tips** ([daily-tips.md](daily-tips.md)): Day-specific strategies
- **Event Guides** ([events.md](events.md)): Event and mini-game walkthroughs
- **Canyon Clash** ([canyon-clash.md](canyon-clash.md)): Weekly PvP strategies
- **About** ([about.md](about.md)): Alliance information

### Posts
All posts go in the `_posts` directory with the naming format: `YYYY-MM-DD-title.md`

## Creating New Posts

### Daily Tips Post
Create a file: `_posts/YYYY-MM-DD-day-tip-title.md`

```markdown
---
layout: post
title: "Your Tip Title"
date: YYYY-MM-DD
categories: daily-tips
tags: [monday, tuesday, etc]
---

Your content here...
```

### Event Guide Post
Create a file: `_posts/YYYY-MM-DD-event-name-guide.md`

```markdown
---
layout: post
title: "Event Guide: Event Name"
date: YYYY-MM-DD
categories: events
tags: [event-name, strategy]
---

Your guide content here...
```

### Canyon Clash Strategy Post
Create a file: `_posts/YYYY-MM-DD-canyon-clash-week-X.md`

```markdown
---
layout: post
title: "Canyon Clash Week X: Map Name"
date: YYYY-MM-DD
categories: canyon-clash
tags: [canyon-clash, pvp]
---

This week's strategy...
```

## Publishing to GitHub Pages

1. **Push to GitHub**:
   ```bash
   git add .
   git commit -m "Add new post"
   git push origin main
   ```

2. **Enable GitHub Pages** (first time only):
   - Go to your repository on GitHub
   - Settings → Pages
   - Source: Deploy from branch `main`
   - Folder: `/ (root)`
   - Click Save

3. **Your site will be live at**: `https://YOUR-USERNAME.github.io/TheElite`

## Local Testing

To test locally before publishing:

```bash
# Install Jekyll (first time only)
gem install bundler jekyll

# Create Gemfile if needed
echo 'source "https://rubygems.org"' > Gemfile
echo 'gem "github-pages", group: :jekyll_plugins' >> Gemfile

# Install dependencies
bundle install

# Run local server
bundle exec jekyll serve

# Visit: http://localhost:4000
```

## Tips

- **Post dates**: Use the actual date for the post - Jekyll will automatically display them
- **Categories**: Stick to `daily-tips`, `events`, or `canyon-clash` for proper organization
- **Tags**: Use descriptive tags to help organize content
- **Images**: Add images to an `assets/images/` folder and reference them in posts

## Need Help?

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Markdown Guide](https://www.markdownguide.org/)
