---
layout: post
title: "My research in Decision Science Laboratory"
date: "2026-02-23 10:00:00"
categories: Acadamic_Performances
tags: National_Taiwan_University
comments: 1
published: true
---

> Awarded with the Distinguished Paper Award at the 2025 International Conference on Management Innovation and Operations Research.

![Post]({{site.baseurl}}/assets/res/ORSTW2.jpg){:height="30%" width="30%"}

**核心焦點：寡佔競爭下的動態訂價**
傳統的訂價模型多建構於獨佔市場與顧客同質性的過度簡化假設上。本研究指出，此框架會嚴重低估生產者剩餘，導致訂價決策偏離利潤最佳化的軌道。

以下為本研究核心貢獻：

- 研究價值： 時效性商品的銷售期具備嚴格的時間限制，企業必須在短時間內，完成精準的需求預測與動態訂價。

- 研究方法： 針對真實世界的寡佔競爭環境，本研究捨棄單一市場假設，導入參考價格效應作為預測顧客願付價格的核心參數，並結合市場區隔，以最大化企業的利潤空間。

- 本研究建構了一套結合機器學習與動態規劃的混合型求解框架，將複雜的市場變數轉化為可運算的數學模型：
  1. 長短期記憶模型 (LSTM) 預測模組： 導入深度學習技術處理歷史銷售時間序列。此模組能在銷售初期，即對顧客的願付價格進行高準確度的收斂與估算。

  2. 混合羅吉特模型： 用於量化多方競爭情境。精準模擬顧客在權衡「市場參考價格」與「異質性偏好」後，所做出的最終選擇機率分佈。

  3. 時變到達率： 揚棄傳統的常數到達率假設，將顧客到達率擴展為時間函數，以精確捕捉產品臨近失效（或出發/展演）時的末期需求躍升現象。

  4. 馬可夫決策過程： 將當前剩餘存貨與競爭對手價格定義為系統狀態。藉由我方訂價影響銷售量變化，並計算出狀態轉移機率。透過此數學推導，模型可直接計算出涵蓋全銷售期數的全局最佳訂價策略。

**應用價值與結論**

本研究的動態訂價架構，成功將顧客異質性與市場動態競爭轉化為可量化的數學參數。這不僅為時效性商品提供了具備高度數學可驗證性的理論支撐，更能在高度不確定、複雜的寡佔市場中，為企業輸出貼近真實商業環境的利潤最大化訂價路徑。

---

**Core Focus: Dynamic Pricing under Oligopolistic Competition**
Traditional pricing models are often built on the oversimplified assumptions of a monopolistic market and customer homogeneity. This study argues that such a framework severely underestimates producer surplus, causing pricing decisions to deviate from the trajectory of profit optimization.

The core contributions of this research are as follows:

- Research Value: The sales horizon of perishable products is strictly time-bound. Enterprises must execute accurate demand forecasting and dynamic pricing within a highly compressed timeframe.

- Methodology: Addressing the real-world environment of oligopolistic competition, this study discards the single-market assumption. Instead, it incorporates the reference price effect as a core parameter for predicting customers' willingness to pay (WTP) and integrates market segmentation to maximize corporate profit margins.

- This study constructs a hybrid solution framework combining machine learning and dynamic programming, translating complex market variables into computable mathematical models:
  1. Long Short-Term Memory (LSTM) Forecasting Module: Introduces deep learning techniques to process historical sales time series. This module achieves high-precision convergence and estimation of customers' willingness to pay, even in the early stages of the sales period.

  2. Mixed Logit Model: Utilized to quantify multi-party competitive scenarios. It accurately simulates the probability distribution of final choices made by customers after weighing the "market reference price" against their "heterogeneous preferences."

  3. Time-dependent Arrival Rate: Abandons the traditional assumption of a constant arrival rate. By extending the customer arrival rate into a time-dependent function, the model precisely captures the late-stage demand surge as the product approaches its expiration (or departure/event date).

  4. Markov Decision Process (MDP): Defines current remaining inventory and competitor price as the system states. By driving sales volume changes through our pricing actions and calculating state transition probabilities, this mathematical derivation allows the model to directly compute the global optimal pricing policy across the entire sales horizon.

**Actionable Value & Conclusion**
The dynamic pricing architecture presented in this study successfully translates customer heterogeneity and dynamic market competition into quantifiable mathematical parameters. This not only provides highly verifiable theoretical underpinning for the pricing of perishable products but also outputs a profit-maximizing pricing path tailored to real-world business environments amidst highly uncertain and complex oligopolistic markets.
