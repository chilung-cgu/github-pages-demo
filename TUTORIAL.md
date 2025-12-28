# GitHub Pages & GitHub Actions 完整教學

這份教學將帶你從零開始，一步步學會如何使用 GitHub Pages 和 GitHub Actions。

---

## 📖 目錄

1. [基礎概念](#-基礎概念)
2. [前置準備](#-前置準備)
3. [Step-by-Step 設定指南](#-step-by-step-設定指南)
4. [驗證與測試](#-驗證與測試)
5. [常見問題](#-常見問題)

---

## 📚 基礎概念

### GitHub Pages 是什麼？

**GitHub Pages** 是 GitHub 提供的免費靜態網站託管服務：

- ✅ **免費** - 完全免費使用
- ✅ **簡單** - 不需要額外的伺服器
- ✅ **HTTPS** - 自動提供安全連線
- ✅ **自訂域名** - 可以綁定你自己的網域

**適合用來做：**
- 個人部落格
- 專案文檔
- 作品集 (Portfolio)
- 簡單的靜態網站

### GitHub Actions 是什麼？

**GitHub Actions** 是 GitHub 的 CI/CD（持續整合/持續部署）工具：

- 🤖 **自動化** - 推送程式碼後自動執行任務
- 🔄 **工作流程** - 定義一系列要執行的步驟
- 🆓 **免費額度** - 公開 repo 免費，私有 repo 有免費額度

**常見用途：**
- 自動部署網站
- 自動執行測試
- 自動建置專案
- 排程任務

---

## 🔧 前置準備

在開始之前，請確保你有：

1. **GitHub 帳號** - [github.com](https://github.com)
2. **Git** - 安裝在你的電腦上
3. **這個專案的檔案** - 已經在你的電腦上

### 確認 Git 已安裝

打開終端機 (Terminal)，輸入：

```bash
git --version
```

如果看到版本號碼（如 `git version 2.39.0`），表示已安裝。

---

## 🚀 Step-by-Step 設定指南

### Step 1: 在 GitHub 上創建新的 Repository

1. 登入 [GitHub](https://github.com)
2. 點擊右上角的 **+** → 選擇 **New repository**
3. 填寫資訊：
   - **Repository name**: `github-pages-demo`（或你喜歡的名稱）
   - **Description**: `學習 GitHub Pages 和 GitHub Actions`
   - **Visibility**: 選擇 **Public**（GitHub Pages 免費版只支援公開 repo）
4. **不要** 勾選 "Add a README file"
5. 點擊 **Create repository**

### Step 2: 初始化本地 Git Repository

在終端機中，進入專案目錄並執行：

```bash
# 進入專案目錄
cd /path/to/github-pages-demo

# 初始化 Git
git init

# 添加所有檔案
git add .

# 建立第一個 commit
git commit -m "Initial commit: GitHub Pages demo project"
```

### Step 3: 連接到 GitHub 並推送

```bash
# 設定遠端 repository（請將 chilung-cgu 替換成你的 GitHub 用戶名）
git remote add origin https://github.com/chilung-cgu/github-pages-demo.git

# 將主分支改名為 main
git branch -M main

# 推送到 GitHub
git push -u origin main
```

💡 **提示**: 如果是第一次使用，GitHub 可能會詢問你的登入資訊。

### Step 4: 啟用 GitHub Pages

1. 在 GitHub 上進入你的 repository
2. 點擊 **Settings**（設定）
3. 在左側選單中點擊 **Pages**
4. 在 **Source** 區塊：
   - 選擇 **GitHub Actions**
   
   > 📍 **位置說明**：在 Pages 設定頁面，你會看到 "Build and deployment" 區塊，
   > 下方有 "Source" 選項，點擊下拉選單選擇 "GitHub Actions"

5. 設定完成後，GitHub 會開始第一次部署

### Step 5: 確認 GitHub Actions 執行

1. 點擊 repository 上方的 **Actions** tab
2. 你應該會看到一個正在執行或已完成的工作流程
3. 點擊進去可以查看詳細的執行記錄

✅ 綠色打勾 = 部署成功
❌ 紅色叉叉 = 部署失敗（點擊查看錯誤訊息）

### Step 6: 查看你的網站

部署成功後，你的網站會在這個網址：

```
https://chilung-cgu.github.io/github-pages-demo/
```

（將 `chilung-cgu` 和 `github-pages-demo` 替換成你的用戶名和 repo 名稱）

---

## ✅ 驗證與測試

### 測試自動部署

試著修改 `index.html`，然後推送更新：

```bash
# 修改檔案後...
git add .
git commit -m "Update: 修改網站內容"
git push
```

然後：
1. 進入 **Actions** tab 查看新的部署是否觸發
2. 等待部署完成
3. 刷新網站確認更新

---

## ❓ 常見問題

### Q: 為什麼我的網站顯示 404？

**可能原因：**
1. Repository 是私有的（需要 GitHub Pro 才能用私有 repo）
2. GitHub Pages 還沒完成部署
3. 檔案路徑有問題

### Q: 部署失敗怎麼辦？

1. 進入 **Actions** tab
2. 點擊失敗的工作流程
3. 查看錯誤訊息
4. 通常是權限設定或檔案問題

### Q: 如何使用自訂網域？

1. 購買一個網域
2. 在 DNS 設定中添加 CNAME 記錄指向 `<username>.github.io`
3. 在 **Settings** → **Pages** 中設定 Custom domain

---

## 🎉 恭喜完成！

你已經學會了：

- ✅ 什麼是 GitHub Pages
- ✅ 什麼是 GitHub Actions
- ✅ 如何創建和部署一個靜態網站
- ✅ 如何設定自動化部署

### 下一步學習建議

1. **客製化網站** - 修改 HTML/CSS 打造你自己的設計
2. **添加更多頁面** - 創建 `about.html`、`contact.html` 等
3. **學習 Jekyll** - GitHub Pages 內建支援的靜態網站生成器
4. **探索更多 Actions** - 如自動測試、自動發布 npm 套件等

---

## 📚 參考資源

- [GitHub Pages 官方文檔](https://docs.github.com/en/pages)
- [GitHub Actions 官方文檔](https://docs.github.com/en/actions)
- [GitHub Actions Marketplace](https://github.com/marketplace?type=actions)

---

有任何問題，歡迎在 [Issues](https://github.com/chilung-cgu/github-pages-demo/issues) 中提出！
