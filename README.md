# PEF v2.0 股票專用版 - 真實台股概率演化回測（最終公開版）

**作者**：你（PEF 框架提出者）  
**AI 協助**：Grok 根據 2026 年 3 月 Phase II 論文規格完整實作  
**日期**：2026 年 3 月 30 日  

本 notebook 完整實作你論文第 3 頁的 `stock_pef_update` 函數，驗證 Cross-Asset Correlation（α=0.6）與 Jump-Diffusion 機制。

## 快速執行（推薦）

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/o581-lab/PEF-Stock-v2.0/blob/main/PEF_v2.0_Stock_Demo.ipynb)

---

## 如何自己跑任何股票（使用說明）

1. 點擊上方 **Open in Colab** 按鈕進入 Colab
2. 找到 `# 抓真實資料` 這個 Cell
3. 修改 `tickers` 這一行即可跑你想看的股票：

```python
tickers = ['2330.TW', '2454.TW', 'NVDA']   # 改成你想跑的股票代碼

範例：
只跑台積電 + 美股領先 → ['2330.TW', 'NVDA']
跑大盤 + 金融股 → ['0050.TW', '2882.TW', 'NVDA']
點選上方選單 Runtime → Run all（全部執行）
等待 20~40 秒，就會自動畫出概率演化曲線和最終概率表
想跑更長時間資料：把 start='2025-01-01' 改成更早的日期即可。

⚠️ 重要風險提醒
本框架僅供學術研究與教育用途，不構成任何投資建議。
股票投資有風險，過去的回測結果不代表未來績效。
使用者必須自行承擔所有投資風險與損失。
作者與本專案不對任何使用本框架所產生的損失負責。
請在使用前充分了解市場風險，並謹慎評估自身風險承受能力。

主要特點
使用真實台股 + 美股領先資料
完整實作論文中的 Cross-Asset Correlation 與 Jump-Diffusion
清晰的概率演化曲線 + 最終概率表
程式碼完全公開、可重現
未來方向
作者正在將 PEF 框架擴展至：
生物 DNA 轉化版
工業 Cyber-Physical 版
歡迎大家 fork、修改、貢獻！

PEF 核心精神：讓不確定性真正演化，而非僅僅預測。

English Version
PEF v2.0 Stock Specialization Edition - Real TAIEX Probability Evolution Backtest
Author: You (PEF Framework Proposer)
Date: March 30, 2026
This notebook fully implements the stock_pef_update function from the paper, validating Cross-Asset Correlation (α=0.6) and Jump-Diffusion.
How to Run Any Stock
Click the Open in Colab button above
Edit the tickers line in the data loading cell
Click Runtime → Run all
⚠️ Risk Disclaimer
This framework is for academic and educational purposes only. It does not constitute any investment advice. Stock trading involves substantial risk. Past performance does not guarantee future results. Users assume all risks and losses. The author and this project are not responsible for any financial losses.
