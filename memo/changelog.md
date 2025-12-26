# 開發日誌 Changelog

---

## 2025-12-26

### Session 1: 專案初始化與基礎建設

#### 時間線

**Step 1: GitHub Repository 建立**
```bash
# 創建 GitHub repo
gh repo create AlexHsieh3/taiwanview --public

# 本地初始化
git init
git remote add origin git@github.com:AlexHsieh3/taiwanview.git
```
- 建立目錄結構：`app/`, `memo/`
- 初始 commit 推送成功

**Step 2: Vue 3 專案建立**
```bash
cd app
npm create vue@latest .
# 選項：TypeScript ✓, Vue Router ✓, Pinia ✓, ESLint ✓, Prettier ✓
npm install
```

**Step 3: Stitch AI 設計轉換**
- 用戶提供 Stitch AI 匯出的「大視界遊覽車有限公司」HTML
- 將靜態 HTML 轉換為 Vue 組件架構
- 主要轉換檔案：
  - `App.vue` - 導航、頁尾、手機選單
  - `HomeView.vue` - 首頁所有區塊
  - `main.css` - Tailwind 樣式

**Step 4: Tailwind CSS v4 配置**
```bash
npm install tailwindcss @tailwindcss/vite
```

⚠️ **遇到問題**：`npx tailwindcss init -p` 失敗
- Tailwind CSS v4 不再使用傳統 config 檔案
- 解決方案：使用 CSS-first 配置

```css
/* main.css */
@import "tailwindcss";

@theme {
  --color-primary: #0EA5E9;
  /* ... */
}
```

⚠️ **遇到問題**：頁面樣式沒有載入（純文字顯示）
- 原因：缺少 `@tailwindcss/vite` 插件
- 解決方案：安裝插件並更新 `vite.config.ts`

```typescript
// vite.config.ts
import tailwindcss from '@tailwindcss/vite'

export default defineConfig({
  plugins: [vue(), vueDevTools(), tailwindcss()],
})
```

**Step 5: Favicon 更新**
- 創建 SVG 格式巴士圖標 (`public/favicon.svg`)
- 更新 `index.html` 使用 SVG favicon

---

### Git Commits 記錄

| Commit | 說明 |
|--------|------|
| `7ea2e9b` | feat: 將 Stitch AI 設計轉換為 Vue 組件 |
| `1fbe994` | feat: 修復 Tailwind CSS 配置並新增開發進度記錄 |
| `feb8037` | feat: 新增巴士圖標 favicon |

---

### 問題與解決方案

#### 問題 1: Tailwind CSS init 命令失敗
```
$ npx tailwindcss init -p
# Exit code 1
```
**原因**: Tailwind CSS v4 改用 CSS-first 配置方式，不再需要 `tailwind.config.js`

**解決**: 在 `main.css` 中使用 `@import "tailwindcss"` 和 `@theme` 指令

---

#### 問題 2: 頁面樣式沒有載入
**症狀**: 網站顯示純文字，沒有任何 CSS 樣式

**原因**: Tailwind CSS v4 需要 Vite 插件來處理 CSS

**解決**:
```bash
npm install @tailwindcss/vite
```
```typescript
// vite.config.ts
import tailwindcss from '@tailwindcss/vite'
plugins: [..., tailwindcss()]
```

---

#### 問題 3: Chrome DevTools MCP 連接失敗
```
Error: The browser is already running for chrome-devtools-mcp/chrome-profile
```
**原因**: 之前的 Chrome 實例仍在運行

**解決**:
```bash
pkill -f "chrome-devtools-mcp/chrome-profile"
```

---

### 檔案變更總覽

```
app/
├── index.html              # 更新 favicon、fonts、meta
├── vite.config.ts          # 新增 Tailwind 插件
├── package.json            # 新增依賴
├── public/
│   └── favicon.svg         # 新增巴士圖標
└── src/
    ├── App.vue             # 主版面重寫
    ├── assets/
    │   └── main.css        # Tailwind v4 配置
    └── views/
        └── HomeView.vue    # 首頁重寫

memo/
├── progress.md             # 專案進度
└── changelog.md            # 開發日誌（本文件）
```

---

### 開發環境

| 項目 | 版本/設定 |
|------|----------|
| Node.js | ^20.19.0 or >=22.12.0 |
| Vue | 3.5.25 |
| Vite | 7.3.0 |
| Tailwind CSS | 4.1.18 |
| TypeScript | 5.9.0 |
| 開發伺服器 | http://localhost:5174/ |

---

### 下一步計畫
1. 配置 Cloudflare Pages 自動部署
2. 更換示意圖片為實際公司照片
3. 實作聯絡表單功能
4. SEO 優化與 Google Analytics
