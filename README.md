# Naviscoot routing data

The routing data behind the Naviscoot app: which roads and paths a bromfiets, a snorfiets and a speed pedelec may use
in the Netherlands, fused from OpenStreetMap and NDW traffic-sign data, plus the Valhalla 3.9.1 graph built from it.

This repository holds no code. The data is in its [releases](../../releases).

## Licence

The data is a database derived from OpenStreetMap, made available under the
[Open Database License (ODbL) 1.0](https://opendatacommons.org/licenses/odbl/1-0/) (full text in `LICENSE`). Any
rights in individual contents of the database are licensed under the
[Database Contents License (DbCL) 1.0](https://opendatacommons.org/licenses/dbcl/1-0/). `DATA_LICENCE.md` lists what
the database covers, its sources and how to credit it.

Contains information from OpenStreetMap, © OpenStreetMap contributors,
<https://www.openstreetmap.org/copyright>. Contains NDW verkeersborden data (CC0 1.0, credit to the Nationaal
Dataportaal Wegverkeer appreciated).

## A release

Each release is tagged `graph-<UTC date-time>` and holds three vehicle units: `nl` (bromfiets), `nl-snorfiets` and
`nl-speed_pedelec`. Per unit:

| Asset | Contents |
|---|---|
| `<unit>.tiles.tar` | Valhalla 3.9.1 graph tiles |
| `<unit>.valhalla.json` | The Valhalla configuration that serves them, from `/repo/routing/build/<unit>/` |
| `<unit>.admins.sqlite` | Valhalla's admin areas |
| `<unit>.fused_access.csv` | Access per OSM way for that vehicle, after fusing OSM, NDW signs and the judgements below |

Next to the units:

| Asset | Contents |
|---|---|
| `SHA256SUMS` | SHA-256 of the 12 unit assets, in `sha256sum -c` format |
| `overrides.csv` | Manual access judgements per OSM way |
| `snorfiets_zones.csv` | Municipal snorfiets decisions, with references to the Staatscourant and Gemeenteblad |
| `DATA_LICENCE.md` | The licence and what it covers |
| `ODbL-1.0.txt` | The full ODbL 1.0 text |

Download one release into a directory and check it:

```sh
gh release download <tag> --repo <owner>/<this repo> --dir graph && (cd graph && sha256sum -c SHA256SUMS)
```
