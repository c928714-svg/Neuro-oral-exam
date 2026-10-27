# 神專口試模擬考場

神經專科醫師口試的模擬練習網站：限時問診與神經學檢查、AI 標準化病人與考官（Google Gemini）、漏問漏做檢討、問診模板與考官題庫。

- 100 題案例：3 題考生回憶的真實考題、97 題依問診模板編寫的練習案例
- 考官題庫約 480 題
- 單一 `index.html`，不需要伺服器或建置步驟

## 部署到 GitHub Pages

1. 登入 GitHub，右上角「+」→「New repository」，名稱例如 `neuro-oral-exam`。
2. 進入新的 repository，按「Add file」→「Upload files」，把 `index.html`、`README.md`、`.nojekyll` 拖進去，按「Commit changes」。
   - `.nojekyll` 是隱藏檔，若電腦看不到可以略過，網站一樣能運作。
3. 到「Settings」→「Pages」：Source 選「Deploy from a branch」，Branch 選 `main`、資料夾 `/ (root)`，按「Save」。
4. 等一到兩分鐘，網址會是 `https://你的帳號.github.io/neuro-oral-exam/`。

注意：免費帳號的 GitHub Pages 需要 public repository，網站和原始碼所有人都看得到（包含真實考題回憶內容）。若不想公開，需使用 GitHub Pro 等付費方案搭配 private repository。

## 設定 Gemini（AI 功能）

1. 到 [Google AI Studio](https://aistudio.google.com/apikey) 建立 API key。
2. 打開網站 →「AI 設定」→ 貼上金鑰 →「儲存」→「測試連線」。
3. 模型預設 `gemini-2.5-flash`；Google 推出新模型時，直接在「AI 設定」改模型名稱即可。

安全性：
- 金鑰只存在你自己瀏覽器的 localStorage，不會寫進 repository，也不會被其他訪客看到；每位使用者要自己輸入自己的金鑰。
- 建議在 Google Cloud Console →「API 和服務」→「憑證」限制這把金鑰：應用程式限制選「網站」並填 `https://你的帳號.github.io/*`，API 限制只允許 Generative Language API。
- 不要把金鑰寫進 `index.html` 再上傳。

沒有金鑰時，按鈕問診、題庫考官、檢討、模板與所有題目都可以正常使用。

## 資料儲存

練習紀錄、題庫自評、AI 生成的案例都只存在各自瀏覽器的 localStorage；換瀏覽器或清除網站資料就會消失。

## 內容說明

練習案例由 AI 依問診模板編寫，非考古題；參考答案依 2026 年 6 月以前的知識，診斷標準與藥物請以最新指引為準。
