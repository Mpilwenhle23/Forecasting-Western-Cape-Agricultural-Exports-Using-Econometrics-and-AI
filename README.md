# Forecasting-Western-Cape-Agricultural-Exports-Using-Econometrics-and-AI
**Repository Description:** Combines econometric VAR models (for ERPT analysis) with AI/ML (XGBoost) to forecast Western Cape agricultural export volumes and competitiveness to model the impact of exchange rates  and climate on trade. A `Stellenbosch Economics 281` portfolio project using Python and R.

---

## 1. The Business Problem (The "Client" Pain Point)

Based on the project brief, Western Cape agricultural exporters (wine, fruit, grain) face a critical paradox: despite a weakening Rand, export volumes are declining, and market share is being lost to competitors in Peru, Turkey, and Australia. (Agricultural Outlook 2018-2027)

This project addresses their core pain points:
* **Pricing & Profitability:** How much of the Rand's depreciation is *actually* passing through to export prices versus being absorbed by margins?
* **Competitiveness:** Are we losing market share despite a currency advantage?
* **Investment Uncertainty:** Exporters are hesitant to make multi-million Rand investments (e.g., in cold storage) without confident sales forecasts.

## 2. Economic Framework (The Academic Anchor)

This analysis is grounded in the development economics frameworks from Stellenbosch University's `Economics 281` module. It specifically applies:
* **Chapter 9: Agricultural Transformation:** Analyzing farmer behavior, risk, and value chains.
* **Chapter 12: International Trade Theory:** Modeling comparative advantage, terms of trade, and export-led growth strategies.

## 3. Part 1: The Classic Econometric Analysis (The Baseline)

This section builds the foundational econometric model required by institutions like the World Bank and Stats SA for *explanatory analysis*.

* **Objective:** To quantify the **Exchange Rate Pass-Through (ERPT)**.
* **Methodology:** A **Vector Autoregression (VAR) model** is implemented as specified in the project brief.
* **Key Steps:**
    1.  **Data Collection:** Sourced from Stats SA (PPI), SARB (Exchange Rates), and UN Comtrade (Competitor Prices).
    2.  **Stationarity:** Used ADF & KPSS tests to confirm all time series are stationary (in first differences).
    3.  **Cointegration:** Applied the Johansen test to identify long-run relationships between variables.
    4.  **Analysis:** Generated **Impulse Response Functions (IRFs)** and **Variance Decompositions** to measure the impact of a 1% Rand depreciation shock on export prices and volumes.

## 4. Part 2: The AI/ML "Upgrade" (The Predictive Value-Add)

Classic econometrics explains *what happened*. AI/ML predicts *what will happen next*. This section "upgrades" the analysis from explanation to a forward-looking commercial tool.

* **Objective:** To build a highly accurate 6-month forecast for export *volumes*.
* **Methodology:** An **XGBoost (Extreme Gradient Boosting)** model, which consistently outperforms traditional time-series models in forecasting competitions.
* **Feature Engineering:**
    1.  **Econometric Features:** Used lagged variables of prices, volumes, and exchange rates identified from the VAR analysis.
    2.  **Alternative Data:** Integrated high-frequency data that VARs struggle with:
        * **Climate Data:** Satellite-derived rainfall and temperature anomalies for the Western Cape (a proxy for supply shocks).
        * **Logistics Data:** Global shipping cost indices (a proxy for supply chain friction).
    3.  **NLP Sentiment (Optional):** Developed a simple "agri-sentiment" index by scraping headlines from `Agbiz.co.za` to capture real-time market news.
