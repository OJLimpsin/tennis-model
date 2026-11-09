# tennis-model

ATP opening-line movement model (`live_move_model_v2`): predicts Pinnacle's open->close move from pre-match player features; bet the side the line is expected to move toward, early, at the best available price.

## Nightly run
```
base64 -d data_bundle.txz.b64 | tar xJ      # once: unpacks data/
python3 nightly.py --snaps <dir of odds CSVs> [--tdi-new <new TDI results CSV> ...] --out picks.csv
```
- Odds: daily CSVs written by the Google Apps Script logger to Drive `Tennis ATP Models/live/snapshots_daily/`.
- Results: Sackmann history (auto-downloaded from the Kadantte/tennis_atp mirror, through RG 2026) + tennis-data 2026 sheet extract (Jun 8 - Jul 31) + TDI ATP-tour results (`data/tdi_hist.csv`, Aug 1 -> Nov 6 2026, plus any new TDI exports).

See the "Tennis betting" Claude project for findings, betting rules and status.
