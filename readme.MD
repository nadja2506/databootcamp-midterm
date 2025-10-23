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
| **ADX (UAE)** | Banking | First Abu Dhabi Bank (FAB) | ADX / Yahoo Finance |
| **ADX (UAE)** | Energy | Abu Dhabi National Energy Co. (TAQA) | ADX / Yahoo Finance |
| **NYSE (U.S.)** | Banking | JPMorgan Chase (JPM) | Yahoo Finance |
| **NYSE (U.S.)** | Energy | ExxonMobil (XOM) | Yahoo Finance |

The dataset includes over **400 trading days** from 2022–2023 with **12+ features**, such as:  
`Date`, `Company`, `Market`, `Sector`, `Close`, `Open`, `High`, `Low`, `Volume`, calculated `Daily Return`, and categorical `Day_Type`.

Data preparation was done in **Python**, using:
- `pandas` for cleaning and transformation  
- `numpy` for descriptive statistics  
- `matplotlib` and `seaborn` for visualization  

All charts below are saved in the `/graphs/` folder and are reproducible from the Jupyter notebook `analysis.ipynb`.

---

## Results

### 1. U.S. vs. UAE Price Trends

![Figure 1: Stock Price Trends](graphs/PriceTrend.png)

The line plots of daily closing prices show clear contrasts between markets. **U.S. stocks (JPM, XOM)** exhibit visible fluctuations with pronounced peaks and troughs, showing high volatility and sensitivity to global news. **UAE stocks (FAB, TAQA)** follow steadier, flatter curves, representing a more stable and policy-anchored environment. The result illustrates the U.S. market’s dynamic nature compared to the UAE’s more measured pace.

---

### 2. Rolling Volatility Over Time

![Figure 2: Rolling Volatility (30-day window)](graphs/30-dayRollingVolatility.png)

Rolling volatility plots capture short-term risk over a 30-day window. **TAQA** and **XOM** display pronounced spikes in early 2022 due to the **Russia–Ukraine war** and oil market disruptions. Although volatility declines in 2023, energy remains more turbulent than banking. **JPM** shows a mid-2023 uptick during the U.S. regional bank crisis, while **FAB** remains remarkably stable. The visual highlights contrasting market responses—U.S. stocks react sharply to shocks, whereas UAE stocks maintain consistency.

---

### 3. Daily Return Distributions

![Figure 3: Distribution of Daily Returns](graphs/ReturnDistribution.png)

Histograms of daily returns reveal bell-shaped distributions centered around zero. **Energy firms (TAQA, XOM)** have wider spreads, reflecting greater price variability, while **Banking firms (FAB, JPM)** cluster tightly near the mean. The difference indicates that energy stocks experienced larger, more frequent swings tied to oil price volatility, whereas banking maintained predictable behavior. U.S. stocks show slightly broader distributions overall, implying higher risk but also potential for greater reward.

---

### 4. Boxplots of Daily Returns

![Figure 4: Boxplots of Daily Returns per Company](graphs/DailyReturnDistributionperCOMP.png)

The boxplots depict the interquartile range of daily returns. **TAQA** and **XOM** show wider boxes and numerous outliers—clear evidence of their exposure to global energy shocks. **FAB** and **JPM** have narrower boxes, emphasizing stability and smaller daily fluctuations. The figure underscores that sectoral exposure outweighs geographical factors in determining volatility, as both energy firms exhibit high dispersion across markets.

---

### 5. Average Daily Returns by Company

![Figure 5: Average Daily Return per Company](graphs/AvgDailyReturnperCOMP.png)

Average daily returns differ significantly across firms. **TAQA** achieved the highest mean return, followed by **XOM**, while **FAB** slightly underperformed with a negative average. These findings align with oil market trends in 2022–2023, where energy outperformed banking due to elevated commodity prices. The pattern also reinforces the risk-return principle—higher variance accompanied stronger profit potential.

---

### 6. Stock-Level Volatility Comparison

![Figure 6: Daily Return Volatility per Company](graphs/DailyReturnVolatilityperCOMP.png)

Using standard deviation as a volatility measure, **TAQA** and **XOM** once again emerge as the riskiest assets, showing wide daily return dispersions. **FAB** and **JPM**, in contrast, have low standard deviations, showing steady performance and resilience against shocks. The contrast highlights how exposure to global energy markets amplifies risk, whereas banking retains its stabilizing role.

---

### 7. Market-Level Volatility (U.S. vs. UAE)

![Figure 7: Market Volatility Comparison](graphs/MarketVolatility.png)

Aggregate volatility data reveal that the **UAE ADX** exhibits a slightly higher average standard deviation (≈0.021) than the **U.S. market** (≈0.018). While the U.S. market is known for responsiveness, its diverse sectoral composition mitigates overall volatility. The UAE’s higher volatility stems from its energy-heavy structure, not from systemic instability. The chart captures this structural distinction between diversification and concentration.

---

### 8. Proportion of Up vs. Down Days

![Figure 8: Up vs Down Days per Market](graphs/NumberofUpandDownDays.png)

During the observed period, the **U.S. market** had more **Up Days (53%)**, while the **UAE market** recorded **more Down Days (57.5%)**. This asymmetry reflects stronger investor optimism in the post-pandemic U.S. economy compared to a cautious, oil-linked UAE sentiment. The trend suggests that market psychology in the U.S. remained expansionary, while in the UAE it was defensive and event-sensitive.

---

### 9. Sector-Level Comparison: Returns and Risk

![Figure 9: Average Return by Sector and Market](graphs/AvgReturnbySectandMarket.png)

Across both markets, **energy outperformed banking**. **TAQA** (UAE energy) achieved the highest mean daily return, followed by **XOM** (U.S. energy). **FAB** underperformed slightly, while **JPM** delivered modest but stable growth. This illustrates how energy’s boom phase, fueled by global price shocks, benefited producers—especially in oil-exporting economies like the UAE.

![Figure 10: Volatility by Sector and Market](graphs/VolatilitybySectandMarket.png)

This bar chart shows that **energy sectors** were consistently more volatile than **banking sectors** in both markets. The UAE’s energy volatility exceeded that of the U.S., reflecting a tighter connection to oil exports. Banking volatility remained similar across geographies, acting as a foundation of stability. The visualization reinforces that while regional context matters, sector exposure drives most of the volatility variation.

---

### 10. Correlation Matrix and Heatmap

![Figure 11: Correlation Heatmap](graphs/CorrelationHeatmap.png)

The heatmap depicts pairwise correlations among all four companies’ daily returns. Cross-market correlations are low, confirming weak integration. **FAB–JPM** show a slightly positive correlation (0.047), suggesting minimal linkage between UAE and U.S. banking. **TAQA–XOM** exhibit mild negative correlation (–0.11), indicating independent energy market movements. Domestic pairings like **FAB–TAQA (0.15)** and **JPM–XOM (0.29)** are also weak, revealing that even within the same economy, sectoral returns move largely independently.

---

### 11. Cross-Sector Correlations

![Figure 12: Cross-Sector Correlation – U.S.](graphs/CrossSectorUS.png)
![Figure 13: Cross-Sector Correlation – UAE](graphs/CrossSectorUAE.png)

These scatter plots reinforce that **U.S. sectors (JPM–XOM)** share moderate positive correlation, likely due to shared macroeconomic factors like inflation and interest rates, while **UAE sectors (FAB–TAQA)** have almost no relationship, highlighting compartmentalized market structures. In short, domestic diversification benefits investors more in the UAE, whereas cross-sector exposure in the U.S. behaves more synchronously.

---

## Conclusion

The comparative analysis between UAE and U.S. markets across 2022–2023 reveals contrasting financial identities. The **U.S. market** is dynamic and globally synchronized, showing sharp responses to geopolitical and macroeconomic shifts. The **UAE market**, on the other hand, demonstrates resilience, gradual movement, and policy-driven stability. Energy stocks such as **TAQA** and **XOM** generated the highest returns but also faced the widest swings, illustrating the volatility-return tradeoff. Banking stocks, **FAB** and **JPM**, maintained low volatility, cushioning the broader markets from instability.

The U.S. market enjoyed more positive trading days, sustained by post-pandemic recovery momentum, while the UAE experienced a higher proportion of declines reflecting investor conservatism. Overall, **sector composition** proved more influential than geography: energy consistently amplified volatility, while banking stabilized performance. Correlation analysis revealed minimal synchronization between countries and sectors, confirming limited market integration and emphasizing the power of diversification.  

These findings suggest that for investors, combining **UAE and U.S. assets** offers significant diversification advantages, balancing U.S. growth potential with UAE stability. For policymakers, the results underline the need for the UAE to diversify beyond energy to reduce vulnerability to global price swings. The U.S., meanwhile, must manage the volatility inherent in its interconnected financial system.  

In essence, the **U.S. market thrives on dynamism**, while the **UAE market succeeds through steadiness**. Their coexistence illustrates how structural diversity strengthens global financial equilibrium, even amid crisis conditions.

---

## Next Steps

1. **Expand Dataset:** Add real estate and telecommunications sectors for further comparison.  
2. **Apply Time-Series Models:** Introduce rolling Sharpe ratios and ARIMA forecasts to study evolving risk patterns.  
3. **Portfolio Analysis:** Simulate diversification benefits using UAE–U.S. mixed portfolios.  
4. **Interactive Dashboards:** Build Plotly/Dash visual dashboards linking macro events to return changes.  
5. **Policy Linkage:** Analyze how regulatory or fiscal actions impact investor sentiment in both economies.

---

### References

- Abu Dhabi Securities Exchange (ADX): TAQA and FAB data (2022–2023)  
- Yahoo Finance API: JPMorgan Chase (JPM), ExxonMobil (XOM)  
- IMF *World Economic Outlook* (2023): Oil price and inflation trends  
- Bloomberg & Federal Reserve (2023): U.S. banking volatility  

---

✅ *All visualizations were generated in `analysis.ipynb` and saved to the `/graphs/` folder for GitHub rendering.*

---
