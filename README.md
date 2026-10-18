# 小柯攝影工作室｜作品集網站

純靜態網站（單一 `index.html`，HTML + CSS + 少量 JS），可直接部署到 Vercel。

## 專案結構

```
.
├── index.html
├── vercel.json
├── README.md
└── images/
    ├── hero.jpg            首頁主視覺（建議 1920×1080）
    ├── about.jpg           關於我（建議 4:5）
    ├── wedding-01~06.jpg   婚紗
    ├── event-01~06.jpg     婚禮紀錄
    └── portrait-01~06.jpg  形象照
```

## 替換成真實圖片

目前 `images/` 內是本機生成的**示意圖**。請用同名檔案覆蓋即可，不需要改 HTML。
免費商用圖庫建議：

- Unsplash：https://unsplash.com（搜尋 wedding couple、bride、portrait）
- Pexels：https://www.pexels.com
- Pixabay：https://pixabay.com

建議：作品圖 4:5 直式、寬 960px 以上、單檔 300KB 以內。
正式上線請換成你自己的作品；使用圖庫圖片請確認授權條款，必要時標註來源。

## 上線前請修改

1. `index.html` 搜尋 `hello@example.com`，換成真實 Email（共 3 處：JSON-LD、頁尾、表單 mailto）
2. 搜尋 `your_instagram`，換成真實 Instagram 帳號（共 2 處）
3. 服務方案價格與加選規則為範例，請依實際情況調整
4. `<head>` 可加上 `<link rel="canonical" href="你的網址">`

## 詢問表單

目前送出後以 `mailto:` 開啟使用者的郵件程式（無需後端）。若想直接收信，可改用 Formspree / Getform：
把 `<form>` 的 `action` 改成服務提供的網址，並移除頁尾的 `<script>`。

## 部署

### GitHub
```bash
git init
git add .
git commit -m "init portfolio site"
git branch -M main
git remote add origin https://github.com/<你的帳號>/<repo>.git
git push -u origin main
```

### Vercel
1. 登入 https://vercel.com，點 **Add New → Project**
2. 匯入剛才的 GitHub repo
3. Framework Preset 選 **Other**，Build Command 與 Output Directory 留空
4. 按 **Deploy**，之後每次 push 會自動更新

## RWD 斷點

- 桌機（> 1024px）：作品三欄
- 平板（769–1024px）：作品兩欄
- 手機（≤ 768px）：作品單欄
