# Privacy policies

One GitHub Pages site for the legal pages of every app, built by GitHub Pages' own Jekyll (no build step):

- `https://ishubhamx.github.io/privacy/`: a list of all apps with links to their pages.
- `https://ishubhamx.github.io/privacy/<app>/`: the app's privacy policy (use this URL in Play Console and in the app).
- `https://ishubhamx.github.io/privacy/<app>/terms/`, `.../licenses/`: extra pages, where an app has them.

| App | Privacy policy |
|---|---|
| Arrow Maze | https://ishubhamx.github.io/privacy/arrow-maze/ |
| Hindu Panchangam | https://ishubhamx.github.io/privacy/hindu-panchangam/ |
| ReplyBro | https://ishubhamx.github.io/privacy/replybro/ |

## Add an app
Each file in `_apps/` is one app; its file name becomes the URL.

**Generated policy** (simple apps): create `_apps/<app-slug>.md`. The text comes from `_includes/policy.html` and `_data/services.yml`.

```yaml
---
layout: app
title: My App                       # name as shown on Google Play
package: com.ssvmakers.myapp
play: https://play.google.com/store/apps/details?id=com.ssvmakers.myapp   # optional
services: [admob]                   # keys from _data/services.yml
on_device: Your notes and settings  # what the app saves only on the device
reset: Settings > Reset             # optional: in-app way to delete that data
events: notes created and deleted   # optional: analytics events (with gameanalytics)
---
```

**Hand-written policy**: create `_apps/<app-slug>.html` with front matter (`title`, `package`, optional `play`, `excerpt_separator: ""`) followed by the full HTML page wrapped in `{% raw %}...{% endraw %}`, like `_apps/replybro.html`.

**Extra pages** (terms, licenses): put each in `<app-slug>/<page>/index.html` and list them in the app's front matter, e.g. `pages: [terms]`. The home page links them.

## Edit shared text
- Developer name, contact email and the generated policies' effective date: `_config.yml`.
- Third-party services (AdMob, GameAnalytics, ...): `_data/services.yml`.
- Sections every generated policy shares: `_includes/policy.html`.
