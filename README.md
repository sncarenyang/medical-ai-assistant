# Medical RAG + Wikipedia QA System（Caren 版）

一個輕量級、使用 **維基百科（Wikipedia）知識＋TF‑IDF 向量檢索** 的醫療問答助手，使用者輸入問題，系統會：  
1. 用 wikipedia 套件查詢相關條目摘要，  
2. 用 TF‑IDF 向量化與餘弦相似度找出最相關的段落，  
3. 在網頁介面上顯示結果。  

**線上 Demo**：  
👉 [https://sncarenyang-medical-rag-demo.hf.space/](https://sncarenyang-medical-rag-demo.hf.space/)

---

## 1. 功能簡介

- 可輸入中英文之疾病、症狀、藥物、穴位等問題，例如：  
  - `covid19`、`胰島素`、`流感`、`四神湯`、`勞宮穴` 等  
- 系統會：  
  - 查詢中文維基百科摘要，  
  - 與內建知識庫做 TF‑IDF 類似度比對，  
  - 顯示相關段落與相似度分數。  
- 介面：  
  - 使用 Gradio 建立網頁 UI，  
  - 顯示使用者問題與 AI 回答，並保留簡單對話歷史。  

（請注意：這只是一個教學與實作範例，不等於醫療診斷系統，僅供參考，實際醫療問題請諮詢醫師。）

---

## 2. 技術架構

- **語言**：Python  
- **RAG 風格檢索**：  
  - 使用 wikipedia 套件取得維基百科條目摘要（設定為 zh 中文）  
  - 使用 sklearn.feature_extraction.text.TfidfVectorizer 以字元層級（`analyzer='char'`）將文本轉為 TF‑IDF 向量  
  - 用 sklearn.metrics.pairwise.cosine_similarity 計算使用者問題與所有段落的相似度  
  - 選出相似度最高的 2 個段落，並過濾相似度大於 0.2 的結果  
- **前端**：  
  - 使用 gradio 建立一個網頁介面，包含：  
    - 問題輸入框  
    - 回答結果顯示框  
    - 一個「送出」按鈕，並保留簡單對話歷史  
- **特色**：  
  - 不使用大型語言模型 API，僅依賴維基百科＋ TF‑IDF，  
  - 可在本地機器運行，適合想理解「檢索式問答」基礎概念的實作範例。  

---

## 3. 安裝與執行（本機運行）

### 3.1 環境設定

建議使用 Python 3.7 以上版本：

```bash
git clone https://github.com/你的帳號/medical-rag-wiki-demo.git
cd medical-rag-wiki-demo

# 建立虛擬環境（可選）
python -m venv venv
source venv/bin/activate   # Linux/macOS
# 或 venv\Scripts\activate  # Windows

# 安裝依賴
pip install -r requirements.txt
