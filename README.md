# Autonex boundary tiles

Map tiles (PMTiles) used by the Autonex portal's sale and service maps.
Only public government boundary data is published here — no customer or
dealership data.

## Releases

Each release holds three files, streamed by the portal's
`/api/boundaries/pmtiles/[layer]` route:

| File | Layer name | Contents |
| --- | --- | --- |
| `autonex-villages.pmtiles` | `LGD_Villages` | villages and towns |
| `autonex-subdistricts.pmtiles` | `LGD_Subdistricts` | tehsils |
| `autonex-districts.pmtiles` | `LGD_Districts` | districts |

### `mp-hierarchy-2026-09`

Madhya Pradesh is one aligned hierarchy: villages and towns from the Survey
of India village layer, each assigned whole to its current tehsil; tehsils and
districts are the union of their villages, so every level nests with no gaps
or overlaps. MP features carry a stable `key` (`v<LGD code>`, `T<tehsil
code>`, `D<district code>`), `kind` (`village`, `town`, `census_town`,
`other`) and official LGD names. Every other state keeps the LGD layers
unchanged.

## Sources

Obtained through [india-geodata](https://github.com/yashveeeeeeer/india-geodata):
Survey of India village polygons, LGD villages / subdistricts / districts,
and the Swachh Bharat Mission urban local body register. Rights in the
underlying data remain with their publishers.

Built with `scripts/boundaries/build_hierarchy.py` and
`scripts/boundaries/build_tiles.py` in the Autonex repository.
