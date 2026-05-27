# Mauritania Administrative Divisions / موريتانيا



## Overview

| Item | Details |
|------|---------|
| Wilaya | 15 |
| Moughataa | 63 |
| Commune | 238 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-27 |
| Website | [openadmindata.org/mr](https://openadmindata.org/mr/) |
| API | [openadmindata.org/api/mr](https://openadmindata.org/api/mr/) |

## Browse by Wilaya

| # | Wilaya | Moughataas | Communes | Link |
|---|----|----|----|------|
| 1 | Adrar | 4 | 11 | [Browse](divisions/adrar-mr07/) |
| 2 | Assaba | 5 | 26 | [Browse](divisions/assaba-mr03/) |
| 3 | Brakna | 6 | 24 | [Browse](divisions/brakna-mr05/) |
| 4 | Dakhlet Nouadhibou | 2 | 6 | [Browse](divisions/dakhlet-nouadhibou-mr08/) |
| 5 | Gorgol | 5 | 31 | [Browse](divisions/gorgol-mr04/) |
| 6 | Guidimagha | 4 | 22 | [Browse](divisions/guidimagha-mr10/) |
| 7 | Hodh Chargui | 8 | 37 | [Browse](divisions/hodh-chargui-mr01/) |
| 8 | Hodh El Gharbi | 5 | 29 | [Browse](divisions/hodh-el-gharbi-mr02/) |
| 9 | Inchiri | 2 | 3 | [Browse](divisions/inchiri-mr12/) |
| 10 | Nouakchott Nord | 3 | 3 | [Browse](divisions/nouakchott-nord-mr14/) |
| 11 | Nouakchott Ouest | 3 | 3 | [Browse](divisions/nouakchott-ouest-mr13/) |
| 12 | Nouakchott Sud | 3 | 3 | [Browse](divisions/nouakchott-sud-mr15/) |
| 13 | Tagant | 3 | 10 | [Browse](divisions/tagant-mr09/) |
| 14 | Tiris Zemmour | 3 | 3 | [Browse](divisions/tiris-zemmour-mr11/) |
| 15 | Trarza | 7 | 27 | [Browse](divisions/trarza-mr06/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-wilaya.json](data/all-wilaya.json) | JSON | All 15 wilaya records |
| [all-moughataa.json](data/all-moughataa.json) | JSON | All 63 moughataa records |
| [all-commune.json](data/all-commune.json) | JSON | All 238 commune records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-wilaya.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['moughataa']} moughataas")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-wilaya.json", "utf-8"));
console.log(`Total: ${data.length} wilayas`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=wilaya, 2=moughataa, 3=commune |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{wilaya-slug}/
divisions/{wilaya-slug}/{moughataa-slug}/
```

Communes are listed inline in each moughataa's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-wilaya links
- [Per-wilaya data](docs/llms-full/) — Full data by wilaya

## Citation

```
Mauritania Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/mauritania-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
