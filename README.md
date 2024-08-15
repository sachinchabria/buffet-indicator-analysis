# Mean-Reversion Based Alpha Generation Using the Buffett Indicator and Yield Spread

## Abstract

In 2001, Warren Buffett claimed that the total US equity market capitalization to GDP ratio (now famously known as the Buffett Indicator) was "the best single measure of where valuations stand at any given moment." This project further tests this hypothesis under a mean-reversion based alpha generation strategy. Additionally, it compares the predictive power of the Buffett Indicator to other common market over/undervaluation proxies, specifically the yield spread between Moody's seasoned Baa Corporate Bond and the 10-year Treasury bond. The results indicate that a simple strategy based on the Buffett Indicator yields a Sharpe ratio of 1.53, significantly outperforming the yield spread-based strategy.

## Review of Existing Literature

### Contributions to Prior Literature

1. **Buffett Indicator**:
   - Though widely recognized among retail investors, the Buffett Indicator lacks extensive background in academic finance literature.
   - Key references:
     - Lleo and Ziemba (2017): Found that a static decision rule, as suggested by Buffett, offers limited predictive power, whereas a time-varying approach performs significantly better.
     - Chang and Pak (2017): Identified superlinear relationships between the Buffett Indicator and GNP across different countries, suggesting its utility in detecting relative valuation discrepancies internationally.

2. **Equity Market Corrections**:
   - The literature on equity market corrections, particularly post-2008 financial crisis, is extensive and multifaceted.
   - Notable works include:
     - Lewis et al. (2010): Explored the social and ethical implications of the 2008 financial crisis.
     - Cornell and Damodaran (2019): Extended the concept of market corrections to the venture capital space.
     - Pelsser (2003): Investigated corrections due to misvaluation, particularly in the form of Convexity Correction.

## Data Collection

The data required for this study was retrieved from readily available sources:
- **Buffett Indicator**: Calculated as the Wilshire 5000 index divided by the US GDP, obtained from the Federal Reserve Bank of St. Louis' Economic Research page.
- **Yield Spread**: The spread between Moody's seasoned Baa Corporate Bond and the 10-year Treasury, also obtained from the Federal Reserve.

All data was processed using common Python libraries (`pandas`, `numpy`, and `matplotlib`). The datasets were cleaned and aligned for analysis.

## Methodology

The methodology involves a comparative analysis between two strategies:
1. **Yield Spread-Based Strategy**:
   - A mean-reversion strategy based on z-scores of the yield spread between Baa Corporate Bonds and 10-year Treasuries.
   - Z-scores are calculated based on simple moving averages over weekly, monthly, and quarterly intervals.

2. **Buffett Indicator-Based Strategy**:
   - A similar mean-reversion strategy based on z-scores of the Buffett Indicator.
   - Simple moving averages are calculated over quarterly intervals, with various z-score thresholds used to generate buy/sell signals.

### Trading Strategy

- **Buy Signal**: Triggered when the z-score is below a specified threshold (indicating undervaluation).
- **Sell Signal**: Triggered when the z-score exceeds a specified threshold (indicating overvaluation).
- **Profit-Taking Mechanism**: Positions are closed when certain profit thresholds or reversal signals are met.

## Results

- **Yield Spread Sharpe Ratio**: 0.79
- **Buffett Indicator Sharpe Ratio (Mean Reversion)**: 1.53
- **Buffett Indicator Sharpe Ratio (Fixed Profit Taking)**: 1.47

## Conclusion

The Buffett Indicator, when applied through a simple mean-reversion strategy, exhibits significant potential for alpha generation, outperforming the yield spread strategy. Key insights include:
- The Buffett Ratio, though simplistic, has merit in identifying market valuations.
- Further research is warranted to optimize the strategy through advanced techniques like hyperparameter tuning and probabilistic capital allocation.

## Next Steps

1. **Hyperparameter Optimization**: Utilize more computational resources to fine-tune strategy parameters.
2. **Experimentation with Moving Averages**: Test different types of moving averages (e.g., exponential, weighted).
3. **Probabilistic Allocation**: Implement a probabilistic approach to capital allocation based on the strength of signals.
4. **Alternative Distributions**: Explore non-normal distributions for defining thresholds.
