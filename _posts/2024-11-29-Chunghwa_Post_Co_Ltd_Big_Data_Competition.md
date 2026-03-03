---
layout: post
title: "Chunghwa Post Co., Ltd. Big Data Competition"
date: "2024-11-29 15:00:00"
categories: Extracurricular_Activities
tags: National_Taiwan_University
comments: 1
published: true
---

> Team Leader of the team with "Creativity Award" and "Special Award by Galaxy Software Services" in the Chunghwa Post Co.,Ltd. Big Data Competition.

![Post]({{site.baseurl}}/assets/res/POST.jpg){:height="30%" width="30%"}

**競賽主題：AWS 雲端架構下之 i 郵箱點位最佳化**

這是我在碩士班第一學期參與2024 郵政大數據競賽之獲獎成果。面對主辦方提供的數百萬筆真實數據，本專案致力於打破傳統主觀選址的限制，透過嚴謹的數據預處理與計量經濟模型，並結合 AWS 雲端運算實務，建構一套兼顧收入增長與覆蓋率的最佳化選址框架。

**合預測與最佳化決策模型**

在龐大的 AWS 運算環境中，為克服大數據處理的執行效率與記憶體最佳化挑戰，團隊建構了三階段的量化分析路徑：

- 多元線性迴歸 ： 針對獲利指標選定的挑戰，模型經特徵工程處理後，精準收斂出影響站點績效的四大核心變數：捷運站鄰近度、捷運站人流總量、周邊便利商店密度，以及區域年齡人口結構，藉此確立了穩健的獲利預測架構。

- ARIMA 時序動態預測： 建立收入基線後，進一步導入自我迴歸積分滑動平均模型。透過分析歷史時序特徵，預測各點位未來可能的滿格風險，為物流調度與硬體擴充提供動態預警機制。

- 非線性規劃： 將顧客行為限制（如：最大願付移動距離）轉化為數學約束條件。模型整合了上述的迴歸與時序預測結果，在兼顧極大化收入與最佳化覆蓋率的雙重目標下，精準標定出全局最佳的擴充點位與應裁撤之低效點位。

**應用價值與結論**

本專案輸出的點位最佳化模型，經測試與真實世界數據展現出高度一致性，其選定之新點位預期寄件量較原始估算大幅提升超過 7.5 倍。憑藉此精準的數據洞察、嚴謹的數學求解邏輯以及清晰的簡報呈現，團隊最終獲得評審高度肯定，榮獲大會**最佳創意獎**及**叡揚數據應用創新獎**，成功將大數據分析轉化為具備高度落地價值的商業決策支援系統。

---

**Competition Theme: i-Mailbox Location Optimization under AWS Cloud Architecture**

This represents the award-winning outcome of my participation in the 2024 Taiwan Post Big Data Competition during the first semester of my master's program. Confronted with millions of real-world data records provided by the organizers, this project aimed to break the limitations of traditional, subjective site-selection methods. Through rigorous data preprocessing, econometric models, and the practical application of AWS cloud computing, we constructed an optimized site-selection framework that balances revenue growth and coverage rate.

**Hybrid Prediction and Optimal Decision Model**

Within the expansive AWS computing environment, to overcome the challenges of execution efficiency and memory optimization in big data processing, the team constructed a three-stage quantitative analysis path:

- Multiple Linear Regression: Addressing the challenge of selecting profitability indicators, the model, after feature engineering processing, precisely converged on four core variables impacting station performance: proximity to metro stations, total passenger flow at metro stations, density of surrounding convenience stores, and regional age demographic structure. This established a robust profitability prediction framework.
- ARIMA Time-Series Dynamic Forecasting: After establishing the revenue baseline, the Autoregressive Integrated Moving Average (ARIMA) model was further introduced. By analyzing historical time-series features, it predicted the potential future full-capacity (stockout) risks of each location, providing a dynamic early warning mechanism for logistics scheduling and hardware expansion.
- Nonlinear Programming: Customer behavioral limitations (e.g., maximum willingness-to-travel distance) were transformed into mathematical constraints. By integrating the aforementioned regression and time-series forecasting results, the model precisely identified the globally optimal expansion locations and the inefficient locations that should be eliminated, achieving the dual objectives of maximizing revenue and optimizing coverage.

**Actionable Value and Conclusion**

The location optimization model output by this project demonstrated high consistency with real-world data upon testing. The expected shipping volume of the newly selected locations increased significantly, exceeding the original estimates by over 7.5 times. Leveraging these precise data insights, rigorous mathematical solving logic, and clear presentation delivery, the team ultimately received high recognition from the judges, winning the **Best Creativity Award** and the **Special Award from Galaxy Software Services**. This success effectively transformed big data analysis into a commercial decision support system with high practical deployment value.
