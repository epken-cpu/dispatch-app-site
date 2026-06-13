# 點工e指簽 — 上架用公開網站（GitHub Pages）

這個資料夾就是要發佈到 GitHub Pages 的靜態網站，提供 App Store / Play Console 要求的公開網址：

| 頁面 | 路徑 | 上架欄位 |
|---|---|---|
| 首頁／行銷 | `/` | Marketing URL |
| 隱私權政策 | `/privacy/` | Privacy Policy URL（**必填**）|
| 服務條款 | `/terms/` | （Apple 訂閱 App 必填 EULA）|
| 客服支援 | `/support/` | Support URL（**必填**）|

## 部署步驟（一次性）

> 假設你的 GitHub 帳號是 `kentools`，repo 命名 `dispatch-app`，
> 完成後網址會是 `https://kentools.github.io/dispatch-app/`。
> （帳號名不同就把下面的 `kentools` 換掉）

1. 在 GitHub 建一個**新的 public repo**，名稱 `dispatch-app`（不要勾 Add README）。
2. 在這個 `site/` 資料夾開終端機，執行：

```powershell
cd "C:\Users\Ken\Ken agent\workspace\Engineering\dispatch_app\site"
git init
git add .
git commit -m "點工e指簽 上架公開頁：隱私權／條款／客服"
git branch -M main
git remote add origin https://github.com/kentools/dispatch-app.git
git push -u origin main
```

3. 到 repo 的 **Settings → Pages**：
   - Source 選 **Deploy from a branch**
   - Branch 選 **main**、資料夾選 **/(root)** → Save
4. 等 1～2 分鐘，重新整理就會看到網址。確認以下四個都打得開：
   - `https://kentools.github.io/dispatch-app/`
   - `https://kentools.github.io/dispatch-app/privacy/`
   - `https://kentools.github.io/dispatch-app/terms/`
   - `https://kentools.github.io/dispatch-app/support/`

## 之後要改內容

直接改這資料夾的 `.html`，再：

```powershell
git add . ; git commit -m "更新內容" ; git push
```

過 1～2 分鐘自動更新。

## 上架欄位怎麼填（對照表）

| 商店欄位 | 填這個 |
|---|---|
| Google Play 隱私權政策 | `https://kentools.github.io/dispatch-app/privacy/` |
| App Store Privacy Policy URL | `https://kentools.github.io/dispatch-app/privacy/` |
| App Store Support URL | `https://kentools.github.io/dispatch-app/support/` |
| App Store Marketing URL（選填）| `https://kentools.github.io/dispatch-app/` |
| App Store EULA（訂閱必填）| `https://kentools.github.io/dispatch-app/terms/` |
