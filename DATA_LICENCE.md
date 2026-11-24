# Data licence

This file covers Naviscoot's routing data. The code is not covered here.

## The derived database: ODbL 1.0

Naviscoot fuses OpenStreetMap with NDW traffic-sign data to decide which roads and paths each vehicle may use. The
result is a database derived from OpenStreetMap. It is made available under the
[Open Database License (ODbL) 1.0](https://opendatacommons.org/licenses/odbl/1-0/). Any rights in individual contents
of the database are licensed under the
[Database Contents License (DbCL) 1.0](https://opendatacommons.org/licenses/dbcl/1-0/).

That database covers:
- `overrides.csv`: manual judgements per OSM way;
- `snorfiets_zones.csv`: municipal snorfiets decisions, compiled from the Staatscourant and Gemeenteblad;
- the fused access CSVs, the rewritten OSM extract and the Valhalla graph tiles built from them;
- the graph releases (`tiles.tar`, `fused_access.csv`, `valhalla.json` and `admins.sqlite` per vehicle unit).

The graph releases in the public Naviscoot data repository are the public copy of the database. Each release carries
`overrides.csv`, `snorfiets_zones.csv`, this file and the full ODbL text (`ODbL-1.0.txt`), and its notes state this
licence. Anyone who uses the Naviscoot app can ask for the database, and a graph release is the answer.

## Sources

| Source | Licence | Attribution |
|---|---|---|
| OpenStreetMap | ODbL 1.0 | © OpenStreetMap contributors, <https://www.openstreetmap.org/copyright> |
| NDW verkeersborden (API v5) | CC0 1.0 | Not required; credit to the Nationaal Dataportaal Wegverkeer is appreciated |
| Municipal decisions (Staatscourant, Gemeenteblad) | Official government publications (copyright status not checked) | The decision references are in the CSV |

## Attribution when you reuse it

Credit OpenStreetMap ("© OpenStreetMap contributors", linked to <https://www.openstreetmap.org/copyright>), and keep
any database you derive from this one under the ODbL.
