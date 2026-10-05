# commit-team.github.io

Hosts the page a ChiTransit shared-location link opens, `https://commit-team.github.io/place?lat=…&lon=…&name=…`,
and the Android App Links file that lets the app open those links directly.

The source of truth is `share-web/` in the ChiTransit repository: change it there and copy it here.
`assetlinks.json` here carries real fingerprints, while the copy in that repo is a template.

- `place/index.html` is the landing page: it opens the app, otherwise the Play Store, plus Google Maps.
- `.well-known/assetlinks.json` holds the **debug** key's fingerprint for now (the stock React Native debug key).
  When the app is in Play Console, add the app signing key's SHA-256 (Play Console → App integrity → App signing)
  and remove the debug one.
- `.nojekyll` is required, or GitHub Pages skips the `.well-known` folder.

Project sites under this account (e.g. `/chitransit-privacy/`) are served alongside this one and are unaffected.
