# site-nanao-kg：南澳知識圖譜

Klesan 群人文地景數位典藏的單頁知識圖譜應用，React 加 D3 Canvas 力導向圖，資料來源為 Google Sheets 流程。

## 狀態

- 開發中（v0.1.0）：目前資料 349 節點、391 邊、0 突破點。
- 資料管線：本地版由 Excel 轉 JSON；上線版為 Google Sheets、Apps Script、GitHub commit（bot 自動更新 `data/graph.json`）。
- 部署：GitHub Pages（Actions 於 push 到 main 時建置），網址 https://scott-lbx.github.io/site-nanao-kg/ （repo 原名 Nan-ao，已更名）。

## 快速開始

```bash
npm install
npm run data      # 從 data/source.xlsx 重建 data.json（需 python3 與 openpyxl）
npm run dev       # http://localhost:5173
npm run build && npm run preview
```

## 目錄

| 路徑 | 內容 |
|---|---|
| `src/` | React 前端（`graph/` 圖譜繪製、`panels/` 面板、`state/` 資料與 URL 狀態、`styles/`） |
| `data/` | 圖譜資料（`graph.json`，自動同步） |
| `scripts/` | `excel_to_json.py` 與 `meta_mapping.py`（meta 對照表） |
| `.github/workflows/` | `deploy.yml`，部署到 GitHub Pages |
| `南澳知識圖譜_詳細規劃_v2.md` | 詳細規劃（v1 為舊版） |

## 主要功能

- Canvas 力導向圖，meta_group 群聚佈局；三層摺疊側欄、搜尋、時間滑桿、關係類型篩選、圖例。
- 突破點視覺（金色光暈與星號）、Minimap、hover 摘要。
- URL 狀態可分享，例如 `?node=武塔&mg=人物&years=1900-2000`。

## 相關 repo

- [site-zhudong-kg](https://github.com/scott-lbx/site-zhudong-kg)：竹東知識圖譜。與本 repo 共用同一套架構（Google Sheets 當 CMS、React、D3 知識圖譜），本 repo 為其南澳案場版本。

## 授權

README 原宣告 MIT License，但 repo 內沒有 LICENSE 檔，授權以未指定處理。
