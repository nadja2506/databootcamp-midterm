# Comparative Volatility and Performance of UAE and U.S. Stock Markets (2022–2023)
*Exploring how risk, return, and sector behavior differ between two major global markets.*

---

## Project Question

**How do the U.S. and UAE stock markets differ in volatility, returns, and sectoral behavior during 2022–2023, and what does this reveal about market stability, risk, and global interdependence?**

---

## Data

### Sources

This analysis uses daily trading data from four companies representing two sectors—**Banking** and **Energy**—in both **U.S.** and **UAE** markets.

| Market | Sector | Company | Data Source |
|---------|---------|----------|--------------|
| **ADX (UAE)** | Banking | First Abu Dhabi Bank (FAB) | ADX / ADX Exchange |
| **ADX (UAE)** | Energy | Abu Dhabi National Energy Co. (TAQA) | ADX / ADX Exchange |
| **NYSE (U.S.)** | Banking | JPMorgan Chase (JPM) | Yahoo Finance |
| **NYSE (U.S.)** | Energy | ExxonMobil (XOM) | Yahoo Finance |

The dataset contains over **400 trading days** between 2022–2023 with 12+ features, including:  
`Date`, `Company`, `Market`, `Sector`, `Close`, `Open`, `High`, `Low`, `Volume`, calculated `Daily Return`, and categorical `Day_Type`.

Data analysis was performed in **Python** using:  
- `pandas` for cleaning and transformation  
- `numpy` for descriptive statistics  
- `matplotlib` and `seaborn` for visualization  

All figures are stored in the `/graphs/` folder and can be reproduced using the Jupyter notebook `analysis.ipynb`.

---

## Results

### 1. U.S. vs. UAE Price Trends

![Figure 1: Stock Price Trends](graphs/PriceTrend.png)

The line plot of daily closing prices highlights distinct market behaviors. U.S. stocks—JPMorgan Chase (JPM) and ExxonMobil (XOM)—show pronounced fluctuations, reflecting global news sensitivity and investor sentiment shifts. Their sharp peaks and dips correspond to periods of financial stress and oil market adjustments. In contrast, UAE stocks—First Abu Dhabi Bank (FAB) and TAQA—exhibit flatter, steadier trajectories, indicating a more policy-anchored and less reactive market. Overall, the figure portrays the U.S. market as dynamic and fast-moving, while the UAE demonstrates steady and conservative momentum.

---

### 2. Rolling Volatility Over Time

![Figure 2: 30-Day Rolling Volatility](graphs/30-dayRollingVolatility.png)

Rolling volatility measured over a 30-day window captures the evolving risk landscape. Energy stocks (TAQA and XOM) experience sharp volatility spikes in early 2022, coinciding with the Russia–Ukraine war and energy supply shocks. Although volatility later subsides, both remain more turbulent than banking stocks. JPM’s mid-2023 volatility bump aligns with the U.S. regional bank instability, while FAB remains calm and consistent. This visualization reveals contrasting reactions: U.S. equities fluctuate dramatically with global uncertainty, whereas UAE equities maintain resilience through stable domestic policy and limited global exposure.

---

### 3. Return Distribution

![Figure 3: Distribution of Daily Returns](graphs/ReturnDistribution.png)

Histograms of daily returns show that most returns cluster near zero, forming nearly normal distributions. Energy stocks (TAQA, XOM) have broader spreads, meaning greater variability and risk. Banking stocks (FAB, JPM) display narrower shapes, implying steadier performance. The wider tails of TAQA and XOM reflect the heightened uncertainty and price volatility during the global energy crisis, while FAB and JPM maintain compact, risk-controlled profiles. In sum, the distribution analysis confirms that energy trades with higher variance, while banking provides predictability and lower risk exposure.

---

### 4. Daily Return Distribution by Company

![Figure 4: Daily Return Distribution per Company](graphs/DailyReturnDistributionperCOMP.png)

The boxplots visualize how each company’s daily returns vary. TAQA and XOM exhibit wider interquartile ranges and more outliers, capturing the volatility inherent to the energy sector. FAB and JPM have tighter boxes and shorter whiskers, reflecting controlled, smaller daily price movements. U.S. companies show slightly broader variation overall, aligning with their higher responsiveness to international shocks. The figure underscores the core insight: while both energy firms are volatile, geographic location amplifies the pattern—TAQA’s larger dispersion points to stronger oil dependence within the UAE economy.

---

### 5. Correlations Between Sectors

#### Banking Sector Correlation

![Figure 5a: Banking Sector Correlation (FAB vs JPM)](graphs/BankingSectonCorr.png)

A scatter plot of FAB versus JPM daily returns reveals almost no linear relationship between the UAE and U.S. banking sectors. The cloud of points is diffuse, with only a slight positive slope. This means that movements in U.S. banking stocks do not significantly predict or mirror those in UAE banking, confirming that regional monetary and regulatory environments dominate domestic performance. It also suggests limited global integration between financial institutions across these markets.

#### Energy Sector Correlation

![Figure 5b: Energy Sector Correlation (TAQA vs XOM)](graphs/EnergySectorCorr.png)

For the energy sector, TAQA and XOM show a weak negative correlation. While both operate in the same industry, differing national contexts drive their prices: TAQA’s performance is heavily influenced by regional production policies and government strategy, while XOM reacts to global oil benchmarks and U.S. supply-demand dynamics. The weak relationship implies that diversification across these companies can mitigate risk, as their returns do not move in tandem.

#### Cross-Sector UAE

![Figure 5c: Cross-Sector Correlation – UAE (FAB vs TAQA)](graphs/CorssSectorUAE.png)

Within the UAE, FAB and TAQA exhibit almost no correlation, reflecting compartmentalized market behavior. The financial sector and energy sector move independently due to differing regulatory drivers and global linkages. This independence suggests that UAE investors benefit from domestic diversification, as downturns in one sector do not necessarily affect the other.

#### Cross-Sector US

![Figure 5d: Cross-Sector Correlation – U.S. (JPM vs XOM)](graphs/CrossSectorUS.png)

In the U.S., JPM and XOM share a modest positive correlation, indicating that both respond somewhat to macroeconomic conditions such as interest rate policy and inflation expectations. Although the relationship is not strong, the data reveal that the U.S. economy’s sectors tend to move more synchronously than those in the UAE, reflecting the interconnected nature of the American market ecosystem.

---

### 6. Correlation Heatmap of Daily Returns

![Figure 6: Correlation Heatmap](graphs/CorrelationHeatmap.png)

The heatmap presents all pairwise correlations among the four companies. Intra-country correlations (FAB–TAQA and JPM–XOM) are weak but slightly stronger than cross-country ones. Notably, FAB–JPM shows a marginal positive relationship, while TAQA–XOM displays a mild negative one. These low correlations confirm that UAE and U.S. markets are largely independent, offering substantial diversification potential. The heatmap also emphasizes that even within the same market, energy and banking sectors behave distinctly, underscoring the structural segmentation of financial and commodity-based industries.

---

### 7. Average Daily Return by Company

![Figure 7: Average Daily Return per Company](graphs/AvgDailyReturnperCOMP.png)

Average daily returns reveal clear performance disparities. TAQA leads with the highest mean return, followed by XOM, then JPM, with FAB slightly negative. Energy stocks’ superior performance reflects elevated oil prices and strong global demand recovery in 2022–2023. Banking’s lower returns align with slower interest income growth and cautious lending. The UAE’s TAQA outperforming U.S. XOM underscores how energy-exporting economies benefited more directly from price shocks. Conversely, FAB’s negative mean return illustrates relative stagnation in the UAE financial sector during this period.

---

### 8. Daily Return Volatility by Company

![Figure 8: Daily Return Volatility per Company](graphs/DailyReturnVolatilityperCOMP.png)

Standard deviation of returns quantifies volatility across companies. TAQA and XOM stand out as the most volatile, consistent with their energy exposure and sensitivity to external shocks. FAB and JPM remain comparatively stable, with lower deviations. While all stocks show similar patterns of energy > banking volatility, the UAE’s energy volatility surpasses the U.S.’s due to stronger reliance on oil-driven revenues. This emphasizes that sectoral exposure, more than geography, determines volatility intensity.

---

### 9. Market Volatility (UAE vs US)

![Figure 9: Market Volatility Comparison](graphs/MarketVolatility.png)

At the market level, ADX (UAE) displays slightly higher average volatility (≈0.021) than the U.S. (≈0.018). This suggests that despite its steady individual stock trends, the UAE market faces greater overall fluctuation, largely attributable to its energy concentration. The U.S. market’s broader diversification cushions systemic volatility. These results show that structural composition—rather than investor behavior alone—dictates the stability of national markets.

---

### 10. Number of Up vs Down Days

![Figure 10: Up vs Down Days per Market](graphs/NumberrofUpandDownDays.png)

When counting Up and Down trading days, the U.S. market had more Up Days (53%) than Down Days (47%), while the UAE showed more Down Days (57.5%) than Up Days (42.5%). This pattern reveals post-pandemic optimism in the U.S. compared to the UAE’s cautious stance amid oil price adjustments. The figure reflects differences in sentiment: U.S. investors sustained growth-driven optimism, while UAE investors remained defensive and event-sensitive during global market turbulence.

---

### 11. Average Return by Sector and Market

![Figure 11: Average Return by Sector and Market](graphs/AvgReturnbySectandMarket.png)
![Figure 12: Volatility by Sector and Market](graphs/VolatilitybySectandMarket.png)

Sector-level comparison reinforces earlier findings: energy outperformed banking in both regions but also bore more volatility. TAQA achieved the highest mean return, while FAB posted the lowest. Energy sectors’ greater fluctuations are consistent with global commodity market dependence, whereas banking remains a stabilizing anchor. The contrast demonstrates that the UAE’s economy is more vulnerable to energy cycles, while the U.S. achieves resilience through diversification. The dual charts collectively highlight that return and volatility move together—confirming the fundamental risk-return tradeoff across sectors and regions.

---

## Conclusion

This comparative study of the UAE and U.S. stock markets during 2022–2023 reveals two contrasting yet complementary financial profiles. The U.S. market is highly dynamic, globally integrated, and responsive to geopolitical and macroeconomic shifts. The UAE market, in contrast, is resilient, policy-driven, and moderately insulated from global turbulence. Energy stocks (TAQA, XOM) generated the highest returns but also the widest fluctuations, reflecting the cost of exposure to oil price volatility. Banking stocks (FAB, JPM) provided stability and acted as buffers against systemic shocks.

The U.S. recorded more upward trading days, fueled by post-pandemic recovery and robust consumer confidence. Meanwhile, the UAE’s higher proportion of down days signaled caution and the influence of global oil market corrections. Sectoral patterns dominated geographical effects: energy consistently drove volatility and profit potential, while banking supplied reliability. Correlation results confirmed that UAE and U.S. markets move independently, reinforcing their diversification benefits.  

For investors, combining UAE and U.S. equities offers an effective risk hedge—balancing U.S. growth potential with UAE steadiness. For policymakers, the findings stress the UAE’s need to diversify beyond energy to enhance resilience, while the U.S. must continue monitoring financial interconnectivity to manage volatility. Ultimately, both markets embody distinct strengths: the U.S. thrives through innovation and risk-taking; the UAE endures through stability and strategic governance. Their coexistence underlines how market diversity sustains global equilibrium.

---

## Next Steps

1. **Expand Dataset:** Incorporate sectors such as real estate, telecommunications, and consumer goods to broaden comparative scope.  
2. **Apply Time-Series Models:** Use rolling Sharpe ratios and ARIMA forecasting to capture evolving risk and performance dynamics.  
3. **Portfolio Simulation:** Evaluate diversification effects by constructing hypothetical mixed UAE–U.S. portfolios.  
4. **Interactive Dashboards:** Develop Plotly/Dash applications linking macroeconomic events to stock movements.  
5. **Policy Evaluation:** Explore how fiscal reforms or monetary tightening influence investor sentiment across both economies.

---

### References

- Abu Dhabi Securities Exchange (ADX): TAQA and FAB data (2022–2023)  
- Yahoo Finance API: JPMorgan Chase (JPM), ExxonMobil (XOM)  
- IMF *World Economic Outlook* (2023): Oil price and inflation trends  
- Bloomberg & Federal Reserve (2023): U.S. banking volatility  

