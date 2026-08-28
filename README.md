# macon-redirect

Keeps `macon.devopsinstitute.id` alive now that MacOn lives at
[macon.id](https://macon.id). Two jobs:

1. **Browsers.** `index.html` and `404.html` are the same page: they send the
   visitor to the same path on macon.id, query string and fragment included.
   GitHub Pages serves `404.html` for every path this repo does not have, so
   one file covers the whole old site.
2. **Old Macs.** MacOn 1.4.1 and earlier check for updates at
   `https://macon.devopsinstitute.id/downloads/version.json`, and they use
   URLSession, which does not run JavaScript. So `downloads/version.json` here
   is a real file, mirrored hourly from macon.id by
   `.github/workflows/sync-feed.yml`. Its `url` points the DMG at macon.id, so
   nothing else needs to exist here.

Do not delete this repo, its `CNAME`, or the `macon.devopsinstitute.id` DNS
record while any pre-1.4.2 install might still be out there.
