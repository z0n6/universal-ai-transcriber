# 🎙️ Universal AI Transcriber (萬用音訊/影片轉錄神器)

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/z0n6/universal-ai-transcriber/blob/main/transcriber.ipynb)

這是一個基於 `faster-whisper` 開發的高效能語音轉錄工具，專為會議記錄、影音創作者、研究人員及 Podcast 製作人設計。只要提供音訊或影片連結，即可利用免費的 Google Colab GPU 資源，一鍵生成高精準度的逐字稿與專業字幕檔。

## ✨ 專案亮點 (Key Features)

* **⚡ 架構解耦與極致 UX**：採用「關注點分離 (Separation of Concerns)」設計，將**耗時的 AI 轉錄**（約需數分鐘）與**快速的檔案渲染**（毫秒級）拆分為獨立步驟。轉錄完成後，資料會自動快取，使用者可無限次秒速匯出不同格式，無需重新等待轉錄。
* **🎯 繁體中文最佳化模型**：經實測比較 Whisper 世代模型，特別鎖定 `large-v2` 版本。相較於 v3，v2 在台灣口音辨識與繁簡轉換的穩定性上表現更佳，大幅減少「幻覺」與無意義語氣詞。
* **🛠️ 全面支援專業工作流**：除了易讀的 DOCX / TXT 逐字稿，更支援精確到毫秒的 SRT / VTT 字幕格式，可無縫匯入 YouTube、Premiere Pro 或 DaVinci Resolve。
* **🛡️ 防呆與安全機制**：內建檔名自動過濾系統 (Input Sanitization)，防止使用者輸入非法字元導致系統崩潰，空白時亦可自動補上時間戳記。

## 🛠️ 技術棧 (Tech Stack)

* **核心語言**: Python 3
* **AI 模型**: `faster-whisper` (CTranslate2 加速引擎) / `Qwen3-ASR`
* **文檔處理**: `python-docx`
* **平台**: Google Colab (利用 T4 GPU 進行 FP16 精度推理)

## 🚀 快速開始 (Quick Start)

1. 點擊上方的 **Open in Colab** 按鈕。
2. **第一步 (初始化)**：點擊執行按鈕，系統將自動配置環境（約 1 分鐘）。
3. **第二步 (AI 轉錄)**：貼上 Podcast 或影片網址（如《股癌》mp3 連結），點擊執行。模型會開始進行高精度轉錄並快取資料。
4. **第三步 (格式匯出)**：自訂檔名並勾選需要的格式（Word/TXT/SRT/VTT），點擊執行後檔案將自動下載。

> **💡 提示**：介面採用 Colab Form 設計，若想檢視原始碼，可點擊 Cell 右上角的 `...` -> `Form` -> `Show code`。
