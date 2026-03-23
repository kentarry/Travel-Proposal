# 🌏 TravelCraft — AI 旅遊計劃書產生器

一鍵生成完整旅遊計劃書，包含每日行程、美食推薦、住宿、預算、匯率、注意事項、行李清單。
所有資料存放在 `data/destinations.json`，任何人都可以輕鬆新增目的地。

## ✨ 功能特色

- 📍 選擇目的地，自動生成多日行程
- 🍜 景點＆餐廳均附評分，高評價優先推薦
- 🔄 每個景點/餐廳可一鍵替換或移除
- 💱 自動顯示出發地對目的地的匯率
- 🧳 完整行李清單＆注意事項
- 💰 依預算等級顯示費用估算
- 📱 手機友好，完全離線運作

## 🚀 使用方式

### 方法一：直接使用
在 Claude 對話中，將 `index.html` 的內容貼入 artifact 即可使用。

### 方法二：本地運行
直接用瀏覽器開啟 `index.html`。

### 方法三：部署到 GitHub Pages
1. Fork 本專案
2. 到 Settings → Pages → Source 選擇 `main` branch
3. 即可透過 `https://你的帳號.github.io/travel-planner/` 使用

## 📂 專案結構

```
travel-planner/
├── index.html          # 主程式（單一 HTML 檔案，含所有邏輯）
├── data/
│   └── destinations.json   # 目的地資料庫
└── README.md
```

## ➕ 如何新增目的地

編輯 `data/destinations.json`，在 `destinations` 陣列中新增一筆：

```json
{
  "id": "unique-id",
  "name": "顯示名稱（例：義大利羅馬）",
  "country": "國家",
  "currency": "貨幣代碼",
  "currencyName": "貨幣中文名",
  "exchangeRates": {
    "TWD": 0.XX,
    "CNY": 0.XX,
    "HKD": 0.XX,
    "USD": 0.XX
  },
  "visa": "簽證資訊",
  "weather": [
    { "months": "1-3月", "desc": "氣候描述" }
  ],
  "tips": ["注意事項1", "注意事項2"],
  "attractions": [
    {
      "name": "景點名稱",
      "area": "所在區域",
      "types": ["文化歷史", "自然風景"],
      "rating": 4.5,
      "price": "門票價格",
      "duration": "建議停留時間",
      "desc": "景點描述"
    }
  ],
  "restaurants": [
    {
      "name": "餐廳名稱",
      "type": "料理類型",
      "dish": "推薦菜色",
      "price": "人均價格",
      "rating": 4.5,
      "area": "所在區域"
    }
  ],
  "hotels": [
    {
      "name": "飯店名稱",
      "level": "經濟/中等/豪華",
      "price": "價格範圍/晚",
      "rating": 4.5,
      "area": "地點",
      "highlight": "特色說明"
    }
  ],
  "budgets": {
    "經濟": { "flight": "機票", "hotel": "住宿/晚", "food": "餐飲/天", "transport": "交通/天", "total": "每人總計" },
    "中等": { ... },
    "豪華": { ... }
  }
}
```

### 資料品質建議
- `rating` 請參考 Google Maps 評分
- `attractions` 建議至少 8-10 個，才能安排 3-4 天不重複
- `restaurants` 建議至少 8 個，涵蓋不同價位和類型
- `types` 使用統一的標籤：文化歷史、自然風景、美食探索、購物血拼、冒險運動、放鬆度假、親子同遊、攝影之旅、藝術體驗、地標景觀

## 🤝 貢獻

歡迎提交 PR 新增目的地！只需要編輯 `data/destinations.json`。

## 📄 License

MIT
