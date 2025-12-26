# 大視界遊覽車網站開發進度

## 專案資訊
- **專案名稱**: taiwanview
- **GitHub**: https://github.com/AlexHsieh3/taiwanview
- **開發伺服器**: http://localhost:5174/
- **部署平台**: Cloudflare Pages

---

## 2025-12-26 開發記錄

### 已完成項目

#### 1. GitHub Repository 建立
- 創建 `taiwanview` repository
- 初始化 Git 並連接遠端
- 建立基本目錄結構 (`app/`, `memo/`)

#### 2. Vue 3 專案建立
- 使用 Vite + Vue 3 + TypeScript
- 整合 Vue Router、Pinia
- 配置 ESLint + Prettier

#### 3. Stitch AI 設計轉換為 Vue
- 將 Stitch AI 匯出的 HTML 轉換為 Vue 組件
- 主要檔案：
  - `src/App.vue` - 主版面（導航、頁尾、手機選單）
  - `src/views/HomeView.vue` - 首頁（所有區塊）
  - `src/assets/main.css` - Tailwind CSS 樣式

#### 4. Tailwind CSS v4 配置
- 安裝 `tailwindcss` 和 `@tailwindcss/vite`
- 配置 `vite.config.ts` 加入 Tailwind 插件
- 使用 CSS-first 配置方式（`@import "tailwindcss"` + `@theme`）

#### 5. 網站區塊
| 區塊 | 說明 |
|------|------|
| Header | 玻璃效果導航列、手機漢堡選單 |
| Hero | 台灣山景背景、「準時、專業、誠信、安全」標語 |
| Features | 四大特色（準時、專業、誠信、安全） |
| Fleet | 車型展示（大型巴士、中型巴士、豪華轎車） |
| Services | 服務項目（環島旅遊、機場接送等 5 項） |
| Testimonials | 客戶評價（3 則） |
| Contact | 聯絡表單 + 公司資訊 |
| Footer | 公司資訊、快速連結、社群連結 |

---

## 公司資訊
- **公司名稱**: 大視界遊覽車有限公司
- **統編**: 24348728
- **電話**: 02-2954-8100
- **傳真**: 02-2954-8101
- **手機**: 0919-906-715
- **服務時間**: 09:00 - 18:00

---

## Cloudflare Pages 部署設定
| 設定項目 | 值 |
|---------|-----|
| Framework preset | Vue |
| Root directory | `app` |
| Build command | `npm run build` |
| Build output directory | `dist` |

---

## 待辦事項
- [ ] 配置 Cloudflare Pages 自動部署
- [ ] 更換圖片為實際公司照片
- [ ] 新增更多車型資訊
- [ ] 實作聯絡表單後端功能
- [ ] SEO 優化
- [ ] 新增 Google Analytics

---

## 技術架構
```
taiwanview/
├── app/                    # Vue 專案
│   ├── src/
│   │   ├── assets/
│   │   │   └── main.css   # Tailwind CSS
│   │   ├── views/
│   │   │   ├── HomeView.vue
│   │   │   └── AboutView.vue
│   │   ├── App.vue
│   │   ├── main.ts
│   │   └── router/
│   ├── index.html
│   ├── vite.config.ts
│   └── package.json
└── memo/                   # 開發記錄
    └── progress.md
```

---

## 相關資源
- [Vue 3 文件](https://vuejs.org/)
- [Tailwind CSS v4](https://tailwindcss.com/)
- [Vite](https://vitejs.dev/)
- [Cloudflare Pages](https://pages.cloudflare.com/)
