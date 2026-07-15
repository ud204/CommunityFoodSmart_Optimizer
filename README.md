# Community FoodSmart Optimizer

A browser-based tool that uses linear-programming / optimization to help with
food planning decisions. Everything runs client-side in `index.html` — open it
in a browser and go.

## The story so far (in the interest of honesty)

I first tried solving this with a **greedy algorithm**, mostly because that was
the first approach that came to mind. It worked, but it was pretty brute-force
and didn't scale well.

A senior colleague suggested I use **[HiGHS](https://highs.dev/)** — a proper
linear-programming / optimization solver — instead, which is what this version
is built on.

**Full disclosure:** I have almost no background in linear programming or
optimization, so the way the problem is modelled (the objective function and
the constraints) may not be set up correctly.

## Help wanted

If you know this area and want to help **fix or improve the equation / the
optimization model**, please go ahead — contributions and corrections are very
welcome. Feel free to open an issue or a pull request.

## What's in here

| File | What it is |
|------|------------|
| `index.html` | The app — UI, model setup, and solver wiring |
| `highs.js` / `highs.wasm` | The [HiGHS](https://highs.dev/) solver (third-party) |
| `xlsx.full.min.js` | [SheetJS](https://sheetjs.com/), for spreadsheet import (third-party) |

## Running it

No build step. Because it loads a WebAssembly file (`highs.wasm`), some browsers
won't run it directly from `file://`. If it doesn't work by double-clicking,
serve the folder locally, e.g.:

```bash
python -m http.server 8000
# then open http://localhost:8000
```
