# Gold-Analysis
Python | SQL | Tableau

# Shifting Fortunes: Unpacking the Behavior of GC=F as a Safe Haven Asset
## Table of Contents
- [Background](#background)
- [Executive Summary](#executive-summary)
- [Methodology](#methodology)
- [Data Analysis](#general-data-analysis)
- [Recommendations](#recommendations)
- [Tableau Dashboard](#tableau-dashboard)


## Background
Gold has long been regarded as a reliable safe haven asset, particularly during periods of economic instability, geopolitical tension, and financial crises. It's historical role as a store of value dates back thousands of years, making it one of the most trusted assets in human history. This perception stems from its unique charateristics, including its intrinsic value, rarity, and resistance to inflation and devaluation.

### Behavioral Dynamics in Times of Crisis
During periods of heightened risk, such as wars, recessions, or pandemics, gold prices typically rise as investors seek stability. Gold has also been perceived as a shield against inflation, maintaining purchasing power over time, especially during periods of high inflation or currency devaluation. As a non-correlated asset, gold often performs independently of traditinoal financial markets reducing overall portfolio risk.

### Objective of Report
This report aims to analyze the behavior of COMEX Gold Futures (GC=F) in response to various crises, assessing its performance as a safe haven asset. By understanding these dynamics, we can better evaluate its role in hedging risk and gain insights into predicting market vulnerabilities during periods of uncertainty. To assess overall market activity, we will use a market proxy (S&P 500) to get a general evaluation of the market.

# Executive Summary
This analysis examines the impact of Federal Reserve rate changes on gold (GC=F) and the S&P 500, alongside an evaluation of gold’s beta behavior over time.

- On the day of a Fed rate cut/hike, gold’s daily return increased 3.6% above its average. In the 7-day event window, gold's return surged by 132% relative to its average, reinforcing its role as a safe-haven asset. Conversely, the S&P 500 exhibited a 40% decline from its average daily return during the event window, but on the day of the event itself, it experienced a sharp 282% increase, indicating heightened market volatility.
- Gold's performance differed during specific monetary actions: the average daily return was 0.07% during rate cuts and 0.04% during rate hikes.
- An analysis of gold's beta (GC=F) highlights its variability over time, reflecting its defensive characteristics. Notable movements include a dip to -0.552 in 2007 during the early stages of the financial crisis, showing a negative correlation with the market, and a peak of 0.822 in 2010 during the post-crisis recovery. From 2018–2023, beta exhibited moderate fluctuations, generally remaining below 1, reinforcing gold's role as a risk diversifier with limited sensitivity to broader market trends during volatile periods.
These findings underscore gold’s unique behavior as a safe-haven asset, providing stability and diversification during periods of economic uncertainty and monetary policy shifts.

# Methodology
For this project, I collected historical GC=F (COMEX Gold Futures) and SPY (S&P 500 ETF) data using the yfinance API, covering the period from January 1, 2000, to January 1, 2024. This extended timeframe was chosen to capture a variety of global events, including recessions, pandemics, and wars, ensuring a robust analysis of the effects of Federal Reserve rate hikes and cuts.

To analyze volatility and market correlation, I used SQL to extract key financial metrics such as beta and RSI from the OHLCV (Open, High, Low, Close, Volume) data. This provided deeper insights into the relationship between SPY and GC=F across varying market conditions.

To enable both long-term and short-term analysis, I developed an interactive Tableau dashboard that allows users to explore GC=F activity at different time granularities—yearly, quarterly, monthly, or daily. This visualization helps highlight trends, correlations, and shifts in gold’s behavior over time.

# General Data Analysis
Here we will analyze GC=F (gold futures) and SPY (S&P 500) behavior, particularly in response to Fed rate hikes/cuts and global events.

## Impact of Fed Rate Cuts/Hikes
<img width="500" alt="Screenshot 2024-12-18 at 11 17 46 AM" src="https://github.com/user-attachments/assets/8a78269d-6caa-4fb4-a90a-93eecfc5fb76" />

Here we see a bar graph showing average daily returns for events (Fed rate cut/hike) event window (7 days before/after event) and non-event. The orange bars represent GC=F returns, while the purple line represents SPY's returns.
1. **GC=F Performance**
  - During the event gold's daily return increased 3.6% to 0.045%
  - During the event window, gold's daily return increased 132% to 0.101%
2. **SPY Performance**
  - During the event SPY's daily return increased 282% to 0.137%
  - During the event window, SPY's daily return decreased 40% to 0.022

This graph provides evidence supporting the claim that gold is treated as a safe-haven asset, behaving independently of broader market fluctuations. The rapid increase in gold’s return during the event window highlights a statistical manifestation of the phenomenon known as risk-off sentiment, where investors, facing periods of stress, become more cautious and shift their portfolios toward secure assets like gold. The sharp increase of 132% in gold’s return during the event window suggests a rush among investors to mitigate risk, while the smaller increase on the actual event day indicates that market participants had already partially priced in the uncertainty.

On the other hand, the SPY’s performance reveals a contrasting dynamic. Although SPY’s daily return increased sharply by 282% during the event, this could reflect a temporary recovery or a broader attempt to stabilize market conditions. However, the 40% decrease in SPY’s return during the event window demonstrates that investor confidence in riskier assets remained fragile. This decline supports the notion that risk-off sentiment persisted beyond the event itself, leading investors to scale back their exposure to equities in favor of safer investments. Together, these patterns highlight the diverging responses of gold and SPY to market stress, underscoring gold’s role as a reliable safe-haven asset in times of crisis.

## GC=F YTY Growth
<img width="500" alt="Screenshot 2024-12-18 at 11 52 32 AM" src="https://github.com/user-attachments/assets/5b9b1b1c-94cf-47d2-8b66-208a1635a71e" />

The YtY growth rate for GC=F (COMEX Gold Futures) shows notable peaks and declines, reflecting gold's role as a safe-haven asset during periods of economic uncertainty:

- In 2007, YtY growth peaked at over 31%, as investors began anticipating the financial instability that would culminate in the 2008 financial crisis.
- Positive returns for GC=F persisted until 2013, when YtY growth dropped by 28.24%. This decline likely reflects a global market recovery from the crisis, as investors shifted toward riskier assets with renewed confidence.
- Another significant surge occurred in 2019 (18.87%) and 2020 (24.59%), driven by the heightened economic uncertainty and market volatility during the COVID-19 pandemic.

## RSI and Beta Analysis
Gold’s Stability vs SPY’s Volatility:

Gold (GC=F) consistently shows a more stable RSI range (45–58), reflecting its role as a safe-haven asset with limited price momentum fluctuations.
In contrast, SPY exhibits higher RSI variability, with peaks above 55–60 signaling stronger bullish momentum and drops near 45 reflecting market downturns.
Beta and RSI Alignment During Crises:

<img width="500" alt="Screenshot 2024-12-18 at 12 40 45 PM" src="https://github.com/user-attachments/assets/4dcb2877-e3b0-4252-abbd-b1ba700fd521" />


Gold’s negative or low beta (e.g., -0.4025 in 2017) indicates its tendency to move independently or inversely to the market during periods of uncertainty.
Elevated gold RSI values (above 55) during times of financial distress (e.g., 2008 crisis and COVID-19 pandemic) suggest increased investor demand for gold as a hedge.
SPY’s higher beta and volatile RSI movements confirm its sensitivity to market sentiment and economic shifts.
Behavior During Recovery Periods:

<img width="500" alt="Screenshot 2024-12-18 at 12 51 04 PM" src="https://github.com/user-attachments/assets/30ad455d-0af1-418f-9609-cbe82a9547a6" />


During post-crisis recoveries (e.g., 2011 peak beta at 0.4142), gold’s correlation with the market temporarily increases as investors re-enter riskier assets.
SPY’s RSI often rises above 55 during these periods, indicating strong bullish momentum in equities.
Investor Sentiment Indicator:

Combining beta and RSI highlights clear patterns:
Gold attracts demand during market downturns (low beta, stable RSI).
SPY reflects broader risk appetite with high momentum variability and stronger correlation to market conditions.


# Recommendations
## Portfolio Diversification Strategy
**Gold as a Safe-Haven Asset:**

Investors should quickly increase their allocation to gold (GC=F) during periods of economic uncertainty. The evidence shows that gold performs well during risk-off sentiment, with a 132% return surge in event windows and notable positive YtY growth during crises like the 2008 financial crisis and the COVID-19 pandemic.
Gold’s low or negative beta highlights its value as a hedge against equity market volatility.
Recommendation: Allocate 10–15% of portfolios to gold during uncertain economic periods to stabilize returns and mitigate downside risk.

SPY for Growth During Recovery:

The S&P 500 (SPY) demonstrates strong bullish momentum during post-crisis recovery periods (e.g., 2011 and 2020), reflected in elevated RSI values (above 55–60) and beta alignment with market trends.
Recommendation: Reallocate toward equities like SPY during economic recoveries or periods of monetary easing to capitalize on high-growth potential.

## Tactical Investment Around Fed Rate Decisions
**Gold for Pre-Event and Event Window Protection:**

The sharp 132% increase in gold returns during the Fed rate change event window (7 days before/after) suggests investors can use gold as a short-term hedge to protect against market volatility.
The smaller 3.6% increase on the event day indicates that much of the uncertainty is priced in beforehand.
Recommendation: Increase gold exposure before Fed rate decisions to benefit from risk-off sentiment and rising returns.

## Monitoring Beta and RSI for Timing Decisions
**Use beta and RSI as key indicators to determine when to shift allocations between gold and equities:**

Low or negative beta for gold (e.g., -0.4025 in 2017) signals it is moving independently or inversely to the market, making it an ideal hedge during risk-off periods.
RSI above 55 for gold indicates strong investor demand, often corresponding to financial crises or uncertainty (e.g., 2008 and 2020).
High RSI for SPY (>55–60) reflects bullish momentum during recoveries, signaling favorable equity market conditions.
Recommendation: Actively monitor beta and RSI trends to adjust allocations dynamically:
Increase gold holdings when beta drops and RSI stabilizes around 50–55.
Shift toward SPY when its RSI rises above 55, signaling a recovery.

## Long-Term vs. Short-Term Allocation
**Short-Term:** Use gold during event windows (rate decisions, crises) to hedge against market volatility and capitalize on its rapid return increases.
**Long-Term:** Maintain a strategic allocation to gold to diversify risk, given its historically stable returns and low correlation with equities. Reallocate to SPY during periods of economic recovery or sustained bullish sentiment.

# Tableau Dashboard

![Dashboard 1 (1)](https://github.com/user-attachments/assets/71065f38-228e-4f4d-b015-19621fdde939)

**Dashboard Link**: https://public.tableau.com/app/profile/bennett.preston/viz/gold_project/Dashboard1


