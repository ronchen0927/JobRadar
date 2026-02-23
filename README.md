# 📡 JobRadar

> 快速搜尋 [104 人力銀行](https://www.104.com.tw/) 職缺的工具，輸入關鍵字即可一鍵搜尋、篩選、瀏覽。

## ✨ 功能特色

- 🔍 **關鍵字搜尋** — 輸入職稱、公司名或技能，快速找到相關職缺
- 📍 **篩選條件** — 依地區（六都）、工作經歷篩選
- ⚡ **非同步爬取** — 多頁同時抓取，速度飛快
- 🌙 **深色 / 淺色模式** — 右上角一鍵切換，自動記住偏好
- 📊 **結果一覽表** — 刊登日期、職位、公司、城市、經歷、學歷、薪水

## 🚀 快速開始

### 1. 環境需求

- Python 3.13+
- [uv](https://docs.astral.sh/uv/) 套件管理工具

### 2. 啟動後端

```bash
cd backend
uv sync                                          # 安裝依賴
uv run uvicorn app.main:app --reload --port 8000  # 啟動 API server
```

### 3. 啟動前端

```bash
cd frontend
python -m http.server 3000   # 或用 npx serve -l 3000
```

### 4. 開始使用

打開瀏覽器前往 👉 **http://localhost:3000**

## 🏗️ 技術架構

| 層級 | 技術 |
|------|------|
| 後端 API | FastAPI + Uvicorn |
| 爬蟲 | aiohttp（非同步） + 104 內部 JSON API |
| 前端 | Vanilla HTML / CSS / JavaScript SPA |
| 套件管理 | uv |

## 📡 API 參考

啟動後端後，可前往 **http://localhost:8000/docs** 查看互動式 API 文件（Swagger UI）。

### 搜尋職缺

```
POST /api/jobs/search
```

```json
{
  "keyword": "Python",
  "pages": 5,
  "areas": ["6001001000"],
  "experience": ["3"]
}
```

### 取得篩選選項

```
GET /api/jobs/options
```

## 📄 授權

MIT License
