# Scenix Games add-on

The game catalogue for the Scenix TV app as a standalone add-on:
browser ports of console and PC classics, a web arcade, and a curated
"Highlighted" row — all as plain data, so the Scenix app repo itself carries no game data.

**Install in Scenix:** Settings → Add-ons → add

```
https://praveshkhatana.github.io/scenix-games-addon/manifest.json
```

The hub fetches `games.json` next to the manifest and shelves every entry in the Games tab;
the app's container strips portal chrome and ads around each game, so only the canvas shows.

Each entry is:

```json
{
  "id": "p2b-01ABC…",
  "title": "Need for Speed: Most Wanted",
  "poster": "https://…jpg",
  "playUrl": "https://…",
  "pad": true,          // plays with a gamepad
  "kb": true,           // keyboard maps
  "touch": false,
  "coi": false,         // multithreaded build — runs in the app's Gecko container
  "ua": "desktop",      // host refuses mobile browsers — answer with a desktop UA
  "tags": ["racing"],
  "desc": "…"
}
```

The catalogue is regenerated from the Scenix hub's build tool (`hub/tools/build-game-addon.js`)
whenever sources change; commit the regenerated `games.json` here and clients pick it up
within six hours.

## Whose content is this?

This repository is **data, not content**. It is a list — titles, poster links and play links
pointing at game pages hosted by third parties. Scenix does not host, own or license any of
the games; the app opens the link, the way a browser does. Game names, artwork and the games
themselves belong to their respective owners and appear here only to identify what a link
points at. What you play, and whether you may play it where you live, is yours to decide and
yours to check — the same rule as every other Scenix add-on: **Scenix is a player, not a
provider.**
