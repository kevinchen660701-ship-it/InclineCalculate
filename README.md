# S2 Chuck 盤面傾角計算器

這個專案是靜態 HTML 計算器，用來計算 S2 Chuck / 晶圓面因 A、V1、V2 三點高度變化造成的盤面傾角、高低點、中心變化、砂輪弧最高變化與 CG T1/T2 位置變化。

## 目前使用網址

- GitHub Pages: https://kevinchen660701-ship-it.github.io/InclineCalculate/
- GitHub repo: https://github.com/kevinchen660701-ship-it/InclineCalculate
- D 槽本機副本: `D:\CodexProjects\InclineCalculate`

## Netlify 狀態

- Netlify 網址: https://inclinecalculate.netlify.app
- Netlify 目前因額度不足，不再作為更新確認來源。
- 之後以 GitHub Pages 為正式線上版本。

## 檔案同步規則

主要 HTML 需要同步四份：

- `index.html`
- `s2_chuck_plane_calculator.html`
- `outputs/index.html`
- `outputs/s2_chuck_plane_calculator.html`

D 槽本機副本也要同步：

- `D:\CodexProjects\InclineCalculate\index.html`
- `D:\CodexProjects\InclineCalculate\s2_chuck_plane_calculator.html`

## GitHub Pages 設定

GitHub Pages 使用：

- Source: `Deploy from a branch`
- Branch: `main`
- Folder: `/(root)`

因為 GitHub Pages 只能選 `(root)` 或 `/docs`，所以根目錄必須保留 `index.html`。

## 目前幾何設定

### FSG-2300 Grind1

- A: `X 0.000, Y +120.000`
- V1: `X +103.923, Y -60.000`
- V2: `X -103.923, Y -60.000`
- CG T1: `X +58.8879, Y -148.000`
- CG T2: `X +58.8879, Y -128.000`

### FSG-2300 Grind2

- A: `X +103.923, Y -60.000`
- V1: `X -103.923, Y -60.000`
- V2: `X 0.000, Y +120.000`
- CG T1: `X -58.888, Y -148.000`
- CG T2: `X -58.888, Y -128.000`

### FSG-150i

- A: `X +87.500, Y -151.554`
- V1: `X -175.000, Y 0.000`
- V2: `X +87.500, Y +151.554`
- CG T1: `X -17.420, Y +140.000`
- CG T2: `X -17.420, Y +160.000`

## 計算備註

- Chuck / 晶圓中心為 `(0, 0)`。
- A 固定不動，V1 / V2 可調整高度。
- V1 / V2 最小調整量固定為 `0.0001 mm`。
- 預設晶圓直徑為 `300 mm`。
- S1 砂輪直徑為 `304 mm`。
- 高低點是在整個圓形晶圓範圍內計算。
- 盤中心變化為傾斜平面在 `(0, 0)` 的 Z 變化。
