# rewardflights.lucy.sh-data

Machine-generated, **web-optimized** award (frequent-flyer) seat-availability
data, derived from [intUnderflow/rewardflights](https://github.com/intUnderflow/rewardflights).

This repo is the data backend of **[rewardflights.lucy.sh](https://rewardflights.lucy.sh)** —
the site fetches these files directly from `raw.githubusercontent.com` at
runtime. Everything here is regenerated automatically by the
[processor](https://github.com/intUnderflow/rewardflights.lucy.sh/tree/main/processor);
**do not edit data files by hand** (changes are overwritten).

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
that's the "data as of" moment — plus a `source` provenance block.

## Freshness & accuracy

Regenerated within seconds of the source dataset changing. Availability is a
point-in-time snapshot provided **as-is**, with no guarantee of accuracy or
bookability, and no affiliation with or endorsement by any airline. Always
verify with the airline before making plans.

## Provenance

Derived from [intUnderflow/rewardflights](https://github.com/intUnderflow/rewardflights).
This dataset carries no license of its own; each file embeds a `source` block
naming the origin repo.
