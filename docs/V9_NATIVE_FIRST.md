# V0.9 Native First

## Status

V0.9 replaces the V0.8 presentation logic with a strict **native-save-first** policy.

## Source-of-truth policy

1. Native Control save evidence is primary.
2. A low GOG Galaxy counter is never negative proof.
3. A GOG counter at or above the official threshold is accepted only as positive proof.
4. GOG `date_unlocked` is authoritative for whether GOG currently reports the achievement unlocked.

## Crisis Management example

Validated development save:

```text
Native save: 3 completed Bureau Alerts / 5
GOG counter: 1 / 5 [stale / advisory only]
Status: INFO
```

If the native save reaches 5 completed Bureau Alerts, the achievement becomes `VERIFIED` regardless of the stale Galaxy value.

## Native evidence currently parsed

- campaign completion markers
- base-game Control Points
- base-game side missions
- Foundation mission completion
- Foundation collectibles
- AWE collectibles
- Foundation hidden-location states
- AWE hidden-location states
- Board Countermeasure CompletedTrials
- distinct completed Bureau Alert mission records

## Repair safety

- save files are read-only
- no user-specific save hash
- save slots evaluated independently
- automatic repair limited to VERIFIED
- INFO repair requires explicit selection plus `I EARNED THESE`
- each successful POST is followed by a fresh achievement GET
- `date_unlocked=null` is never sent

## Source snapshot

The exact V0.9 source snapshot is archived in:

`archive/Control_GOG_Achievement_Repair_V9_NATIVE_FIRST.go.gz.b64`

Reconstruction instructions are in `archive/README.md`.
