# Naol Trading News (XAUUSD · BTCUSD · ETHUSD)

- `index.html` — website (GitHub Pages). Reads `events.json` every minute; shows built-in list if no feed.
- `mt5/NewsExporter.mq5` — EA: MT5 calendar -> `events.json` (+ optional push to this repo).
- `mt5/NewsFilter.mqh` — news filter for your bot: `#include "NewsFilter.mqh"`, then `NF_Panel(); if(NF_Blocked()) return;`

## GitHub Pages
1. Create a repo, upload everything in this folder (keep `index.html` at the root).
2. Settings -> Pages -> Deploy from branch `main` / root.

## MT5
1. Copy `mt5/NewsExporter.mq5` to `MQL5/Experts`, `mt5/NewsFilter.mqh` to `MQL5/Include` (or next to your bot). Compile in MetaEditor.
2. Optional auto-upload: set `GhRepo` (`user/repo`) and `GhToken` (fine-grained token, this repo only, Contents: Read and write); allow `https://api.github.com` in Tools -> Options -> Expert Advisors -> WebRequest.
3. Calendar functions do not work in Strategy Tester (as far as known): test on demo.
