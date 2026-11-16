# Token Radar — make.fun token-radar-01

A ranked radar of pre-token DeFi protocols: every protocol on the snapshot's watchlist
plus the pre-token protocols below its floor, ranked by an implied value computed from
TVL, seven-day growth and how long the protocol has run with no token on record.

- `main.ts` reads `/input/snapshot.json` and writes `board.json`, the dashboard data,
  the dashboard itself and the dossier.
- `dashboard/` is a static page (no framework, no network) with a sortable board,
  a filter and a per-protocol detail drawer carrying the model's own inputs and the
  protocol's farm plan.
- The value model lives in `lib/model.ts`; no protocol name is special-cased.

Run locally:

    mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts --input input/snapshot.json
