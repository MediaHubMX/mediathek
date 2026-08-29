# Mediathek

The ARD Mediathek without the frills: rows, search, series with their
episodes, subtitles, a player that remembers where you stopped. One HTML file, no
build step, built on the [mHub Browser API](https://mhub.mx/mhub-api.md)
and the [`ard-mediathek` addon](https://www.mhub.mx/ard-mediathek/mhub-addon.json)
in Addon Protocol v2.

It is meant as the template for "a site of your own on top of one addon":
the addon does the scraping, the page does the looks, and inside an mHub
browser the host does search, back, immersive playback and storage.

```
npm start      # http://localhost:3004
```

The page works in a plain browser too, because the addon and the ARD CDN
answer with CORS headers. Inside an mHub browser the same code additionally
uses `mhub.fetch`, `mhub.openStream`, `mhub.setSearch`, `mhub.setBackHandler`,
`mhub.setImmersive` and `mhub.storage`.

`MHUB_SITE_ENDPOINTS` lists every domain this page answers on (comma
separated) for `/mhub-site.json`; unset means the one it was asked on.
