---
layout: post
title: "Investment Portfolio Recommendation by AHP and LINE Bot @ NCKU"
date: "2024-01-20 16:00:00"
categories: Acadamic_Performances
tags: National_Cheng_Kung_University
comments: 1
published: true
---

> Achieving 59% accuracy in predicting real-world market trends using a hybrid AHP and PCA model.

![First]({{site.baseurl}}/assets/res/AHP.png){:height="50%" width="50%"}

**專題核心：結合層級分析法 (AHP) 與 LINE Bot 之個人化投資推薦系統**

本專題聚焦於台灣證券交易市場，指出目前的投資推薦系統多側重於機器學習與時間序列預測，往往忽略了投資者個人的風險偏好與主觀經驗。本專案透過整合決策分析理論與行動通訊技術，開發出一套能針對半導體產業提供個人化投資組合建議的系統。

以下為本專題之核心貢獻：

- 研究價值： 針對台灣近十年大幅增長的股票交易需求，建立一個能將財務指標與使用者喜好量化整合的決策框架。

- 技術實作： 利用 LINE Bot 作為前端互動介面，降低一般投資者進入量化分析的門檻，實現即時且便利的投資組合推薦。

**專題方法：多準則決策與維度縮減技術**

本專題建構了一套嚴謹的量化路徑，將龐大的財務數據轉化為可執行之投資策略：

1. 財務數據蒐集與預處理： 從台灣經濟新報 (TEJ) 等資料庫下載半導體產業之股票數據，並針對各項關鍵財務指標進行清理

2. 主成分分析 (PCA)： 由於財務指標眾多且具相關性，本研究導入 PCA 技術進行維度縮減，從繁雜的數據中萃取出最具影響力的核心特徵，優化後續模型的運算效率

3. 層級分析法： 本系統之核心算法。透過設計問卷擷取使用者的主觀權重，並與客觀財務數據結合。藉由成對比較矩陣確保決策的邏輯一致性，計算出各股票的優先順序

4. LINE Bot 整合開發： 將後端決策模型透過 API 與 LINE 通訊軟體對接，使用者只需透過簡單的按鈕與問卷回饋，系統即可自動產生對應的投資組合表單

**應用價值與結論**

本專題成功將傳統的學術決策工具（AHP）與現代行動應用（LINE Bot）結合。實驗結果顯示，該系統能有效納入使用者的經驗價值，並產出比單一模型更貼近個人需求的推薦結果，讓使用者能根據當前的財務趨勢（PCA 結果）與自身偏好（AHP 權重）做出更具一致性的配置，提升了投資決策的透明度與效率。

---

**Core Focus: Personalized Investment Recommendation System Integrating Analytic Hierarchy Process (AHP) and LINE Bot**

Focusing on the Taiwan stock market, this project addresses the limitation of current investment recommendation systems, which often prioritize machine learning and time-series forecasting while neglecting individual investors' risk preferences and subjective experiences. By integrating decision analysis theory with mobile communication technology, this project developed a system that provides personalized portfolio recommendations specifically for the semiconductor industry.

Core Contributions:

- Research Value: Established a quantitative decision-making framework that integrates financial indicators with user preferences, addressing the surging demand for stock trading in Taiwan over the past decade.

- Technical Implementation: Utilized a LINE Bot as the front-end interactive interface to lower the barrier to entry for general investors regarding quantitative analysis, enabling real-time and convenient portfolio recommendations.

**Methodology: Multi-Criteria Decision Making and Dimensionality Reduction**

This project constructed a rigorous quantitative pipeline to transform massive financial datasets into actionable investment strategies:

1. Data Collection and Preprocessing: Extracted stock data for the semiconductor industry from databases such as the Taiwan Economic Journal (TEJ) and performed data cleaning on key financial indicators.
2. Principal Component Analysis (PCA): Given the high volume and correlation of financial indicators, PCA was introduced for dimensionality reduction. This extracted the most impactful core features from complex data to optimize the computational efficiency of subsequent models.
3. Analytic Hierarchy Process (AHP): The core algorithm of the system. It captured users' subjective weights through designed questionnaires and integrated them with objective financial data. Logical consistency in decision-making was ensured via pairwise comparison matrices to calculate the priority ranking of individual stocks.
4. LINE Bot Integration: Connected the back-end decision model with the LINE messaging app via API. Users can automatically generate tailored portfolio forms simply through button clicks and questionnaire feedback.

**Application Value and Conclusion**

This project successfully combined a traditional academic decision-making tool (AHP) with a modern mobile application (LINE Bot). Experimental results demonstrated that the system effectively incorporates users' experiential value, generating recommendations that align more closely with personal needs compared to single-model approaches, allowing users to make more consistent asset allocations based on current financial trends (PCA results) and their personal preferences (AHP weights). These efford could enhance the transparency and efficiency of investment decisions.
