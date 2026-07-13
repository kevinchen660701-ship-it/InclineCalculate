# S2 Chuck Plane Calculator Notes

## Project

- App name: S2 Chuck 盤面傾角計算器
- Netlify site: https://inclinecalculate.netlify.app
- GitHub repo: https://github.com/kevinchen660701-ship-it/InclineCalculate
- Netlify publish directory: `outputs`
- Main deployed file: `outputs/index.html`
- GitHub Pages source: branch `main`, folder `(root)`. Root `index.html` is a copy of `outputs/index.html`.
- Local repo used for GitHub/Netlify: `C:\Users\kevin.DOMAIN1\Documents\Codex\2026-07-07\new-chat\work\InclineCalculateRepo`
- Original working HTML copies:
  - `outputs/s2_chuck_plane_calculator.html`
  - `outputs/index.html`

## Calculation

- Chuck center is the coordinate origin: `(0, 0)`.
- Z change is calculated from:
  - plane before adjustment from A/V1/V2 before Z values
  - plane after adjustment from A/V1/V2 after Z values
  - `deltaPlane = afterPlane - beforePlane`
- A is fixed. V1 and V2 are adjustable.
- V1/V2 minimum adjustment increment is fixed at `0.0001 mm`.
- Default S2 chuck diameter is `300 mm`.
- Highest/lowest chuck values are calculated over the circular chuck face.
- Center change is `deltaPlane` at `(0, 0)`.

## UI Notes

- Summary cards show unit in the title as `(mm)`.
- Summary card unit text below the value is hidden to keep the top information row narrow.
- CG T1 starts on the second summary row; CG T2 follows it.
- Fixed support information displays A/V1/V2, and displays T1/T2 when the selected machine has CG points.
- CG T1/T2 plot labels use a smaller right-side label offset so the text sits next to each point.

## FSG-2300 Grind1

- Support PCD radius: `120 mm`
- A: `X 0.000, Y +120.000`
- V1: `X +103.923, Y -60.000`
- V2: `X -103.923, Y -60.000`
- V1/V2 distance: `207.846 mm`
- S1 wheel diameter: `304 mm`
- S1 wheel radius: `152 mm`
- Previous S1 wheel center before latest 2026-07-13 correction: `X -103.923, Y +103.923`
- S1 wheel center used in drawing/calculation: `X -100.5321, Y +113.000`

### FSG-2300 Grind1 CG T1/T2 Points

Source drawing: `FSG-2300 G1CG相對Chuck圓心距離.jpg`

- Chuck center is `(0, 0)`.
- Upper point is T2.
- Lower point is T1.
- T1: `X +58.8879, Y -148.000`
- T2: `X +58.8879, Y -128.000`
- T1/T2 Z change should be calculated using `deltaPlane`.

## FSG-2300 Grind2

- Support PCD radius: `120 mm`
- A: `X +103.923, Y -60.000`
- V1: `X -103.923, Y -60.000`
- V2: `X 0.000, Y +120.000`
- V1/V2 distance: `207.846 mm`
- S1 wheel diameter: `304 mm`
- S1 wheel radius: `152 mm`
- S1 wheel center used in drawing/calculation: `X +107.480, Y +107.480`
- This center keeps the S1 wheel arc passing through chuck center `(0, 0)` with radius `152 mm`, using a 135 degree intermediate direction between the last two visual trials.
- CG T1: `X -58.888, Y -148.000`
- CG T2: `X -58.888, Y -128.000`

## FSG-150i

- Single Grind option only. No Grind1/Grind2 selector.
- Support PCD radius: `175 mm`
- A: `X +87.500, Y -151.554`
- V1: `X -175.000, Y 0.000`
- V2: `X +87.500, Y +151.554`
- V1/V2 distance: `303.109 mm`
- S1 wheel diameter: `304 mm`
- S1 wheel radius: `152 mm`
- S1 wheel approximate center used in drawing/calculation: `X +152, Y 0`
- CG T1: `X -17.420, Y +140.000`
- CG T2: `X -17.420, Y +160.000`

## Deployment

Netlify is connected to GitHub. Updating the site is:

```powershell
cd C:\Users\kevin.DOMAIN1\Documents\Codex\2026-07-07\new-chat\work\InclineCalculateRepo
git add .
git commit -m "update calculator"
git push
```

Netlify automatically deploys pushes to `main`.

GitHub Pages can be enabled from repo Settings > Pages with `Deploy from a branch`, branch `main`, folder `(root)`.
