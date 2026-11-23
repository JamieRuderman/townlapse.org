# Downtown Santa Rosa

townlapse.org/downtownsantarosa: Railroad Square to Old Courthouse Square and E St, 1st St to 7th St.

Built with the [townlapse](https://github.com/unotdys/townlapse) template's own scripts, laid out to live in one folder:

| File | What it is |
| --- | --- |
| `config.json` | Title, area polygon, map orientation (Fourth Street runs up the screen), street labels |
| `history.json` | Hand-researched places, each with sources in `links` |
| `suggestions_applied.json` | Accepted public suggestions (additions + corrections) |
| `osm_current.json` | Today's businesses from OpenStreetMap (`python3 fetch_osm.py`) |
| `geocache.json` | Address → [lat, lng] cache (Nominatim) |
| `template.html` | The template's `web/index.html`, unchanged |
| `index.html`, `places.json` | Build output (`python3 build.py`) |

To rebuild after editing data: `python3 fetch_osm.py` (optional, refreshes today's places), then `python3 build.py`.

Suggestions: `config.json` → `api.url` is empty, so "Suggest a place" opens this repo's suggestion issue form with the
town (`hub.slug`) filled in. With `api.url` set, the page posts to `api.url + "/suggest"` with `town` in the body.
`template.html` differs from the template's page only in sending that town.
