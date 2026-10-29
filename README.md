# Privacy policies

One GitHub Pages site for all SSV Makers apps, built by GitHub Pages' own Jekyll (no build step):

- `https://ishubhamx.github.io/privacy/`: one combined policy covering every app.
- `https://ishubhamx.github.io/privacy/<app>/`: each app's own policy, e.g. `/arrow-maze/`.

Use either URL in Play Console and in the app's settings; both meet Google Play's requirements.

## Add an app
Create `_apps/<app-slug>.md`; the file name becomes the URL:

```yaml
---
title: My App                       # name as shown on Google Play
package: com.ssvmakers.myapp
services: [admob]                   # keys from _data/services.yml
on_device: Your notes and settings  # what the app saves only on the device
reset: Settings > Reset             # optional: in-app way to delete that data
events: notes created and deleted   # optional: analytics events (with gameanalytics)
---
```

## Edit shared text
- Developer name, contact email and effective date: `_config.yml`. Change `updated` whenever the text changes.
- Third-party services (AdMob, GameAnalytics, ...): `_data/services.yml`. Add an entry before listing a new service in an app.
- Sections every policy shares: `_includes/policy.html`.
