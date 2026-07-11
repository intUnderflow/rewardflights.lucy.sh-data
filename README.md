# rewardflights.lucy.sh-data

Machine-generated, **web-optimized** award (frequent-flyer) seat-availability
data, derived from the open dataset at
[intUnderflow/rewardflights](https://github.com/intUnderflow/rewardflights).

This repo is the data backend of **[rewardflights.lucy.sh](https://rewardflights.lucy.sh)** —
the site fetches these files directly from `raw.githubusercontent.com` at
runtime. Everything here is regenerated automatically by the
[processor](https://github.com/intUnderflow/rewardflights.lucy.sh/tree/main/processor);
**do not edit data files by hand** (changes will be overwritten).

## Format

See [`FORMAT.md`](FORMAT.md) (regenerated alongside the data, so it always
matches) for the full schema. The short version:

| File | Purpose |
|------|---------|
| `manifest.json` | Tiny stable entrypoint: current version, counts, mode |
| `availability.json` | The whole calendar dataset in one file (nibble-per-day encoding) |
| `origins/<ORIGIN>.json` | Same shape, filtered to one origin metro |
| `flights/<ORIG>/<DEST>/<YYYY-MM>.json` | Per-flight detail (where the source has it) |
| `changes/recent.json` | Rolling feed of recently opened/closed award space |
| `places.json` | IATA metro code → city name / country / search aliases |

Every file embeds `v` (source commit SHA) and `t` (source commit time) —
that's the "data as of" moment.

## Freshness & accuracy

Regenerated within ~30 minutes of the source dataset changing. Availability
is a point-in-time snapshot provided **as-is**, with no guarantee of accuracy
or bookability, and no affiliation with or endorsement by any airline.
Always verify with the airline before making plans.

## License

Derived from the [intUnderflow/rewardflights](https://github.com/intUnderflow/rewardflights)
database. The **database** is licensed under the
[Open Database License (ODbL) v1.0](LICENSE) (share-alike), and any
**individual contents** under the
[Database Contents License (DbCL) v1.0](DbCL-1.0.txt).

If you publicly use an adapted version of this database, you must also
license it under ODbL and credit:
*"Contains data from [intUnderflow/rewardflights](https://github.com/intUnderflow/rewardflights),
© its contributors, Open Database License (ODbL) v1.0."*
