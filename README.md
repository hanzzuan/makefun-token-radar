# Token Radar

A pre-token protocol radar for make.fun's token-radar-01 bounty: it reads the sealed
DefiLlama snapshot, ranks every protocol that records no token by an implied launch
value, and hands in a web dashboard with a farm plan for each row.

- `main.ts` — the program (Node 22, standard library only). Reads the snapshot from
  `/input/snapshot.json`, writes `board.json`, `data.js`, the dashboard and the
  screenshots to `/output`, and `dossier.json` last.
- `lib/model.ts` — the radar-2 model: implied value = TVL x category revenue multiple
  x growth multiplier x multichain breadth multiplier x maturity multiplier. No protocol
  name is special-cased; wrapped/staked products of tokens that already trade, CEXes and
  versioned duplicates are kept off the board.
- `dashboard/` — the board: sortable and filterable, a detail view per protocol with the
  model's own inputs and a 7-step farm plan, and the live-token protocols set aside at
  their market cap.
- `vendor/makefun-board.ts` — the kit's dossier library, unchanged.
- `screenshots/` — the board, a detail view and a filtered view, rendered from the
  built dashboard.

MIT licensed.
