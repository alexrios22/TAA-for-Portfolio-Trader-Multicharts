# Tactical Asset Allocation Strategies

This repository contains a collection of Tactical Asset Allocation (TAA) and Rotational strategies implemented for **Portfolio Trader in MultiCharts**. These strategies dynamically allocate assets based on various momentum, volatility, and correlation signals to optimize portfolio performance.

## Overview

Tactical Asset Allocation strategies aim to improve risk-adjusted returns by rotating between different asset classes based on quantitative signals rather than maintaining static allocations. The implementations here follow research from leading quantitative finance experts and have been adapted for practical trading systems.

## Strategies Included

### Core Strategies

- **AAA (Adaptive Asset Allocation)**: Tactical asset allocation strategy from the team at GestaltU and ReSolve Asset Management as described in the paper "Adaptive Asset Allocation: A Primer"
- **BAA (Bold Asset Allocation)**: Momentum-based strategy with protective canary universe
- **DAA (Defensive Asset Allocation)**: 3-universe strategy with Crash Protection Factor (CPF)
- **EAA (Elastic Asset Allocation)**: 7 Golden Models with correlation-hedged scoring
- **FAA (Flexible Asset Allocation)**: Momentum, volatility, and correlation-based ranking
- **GEM (Global Equity Momentum)**: Dual momentum strategy (Absolute + Relative)
- **GPM (Generalized Protective Momentum)**: Correlation-hedged momentum with crash protection
- **GTAA (Global Tactical Asset Allocation)**: Fixed allocations with SMA trend filters
- **HAA (Hybrid Asset Allocation)**: 3-universe strategy with hybrid CPF calculation
- **IA (Inercia Alcista)**: Based on the work of Javier Alfayate
- **IBS (Internal Bar Strength)**: Based on work by Oddmund Groette from Quantified Strategies
- **PAA (Protective Asset Allocation)**: CPF-based protection with stock/bond allocation
- **VAA (Volatility Adjusted Allocation)**: Bond fraction based on negative momentum count

## File Organization

All strategy files are organized in the root directory:
- `*Calculate*.txt`: Utility functions for calculations, matrix operations, and indicators
- `*Signal_Base.txt`: Core signal generation logic for each strategy
- `*Portfolio_MM.txt`: Portfolio money management implementations with rebalancing logic

Additional MultiCharts portfolio files are provided in the `Portfolio Trader Multicharts/` folder with pre-configured strategy settings.

## References

### Primary Research
- **TrendXplorer (Jan Willem Keuning)**: https://papers.ssrn.com/sol3/cf_dev/AbsByAuth.cfm?per_id=1935527
- **Adaptive Asset Allocation: A Primer** (Adam Butler - GestaltU & ReSolve Asset Management)
- **Defensive Asset Allocation** (Dr. Wouter Keller and JW Keuning)
- **Global Equity Momentum** (Gary Antonacci)
- **Flexible Asset Allocation** (Dr. Wouter Keller and Hugo Van Putten)
- **Elastic Asset Allocation** (Dr. Wouter Keller and Hugo Van Putten)
- **Bold Asset Allocation** (Dr. Wouter Keller)
- **Hybrid Asset Allocation** ( Dr. Wouter Keller and JW Keuning)

### Strategy-Specific References
- **IBS (Internal Bar Strength)**: Oddmund Groette - https://www.quantifiedstrategies.com
- **IA (Inercia Alcista)**: Javier Alfayate (https://www.amazon.com/-/es/Javier-Alfayate-Gallardo-ebook/dp/B089RJ3G2F)
- **AAA**: GestaltU and ReSolve Asset Management - "Adaptive Asset Allocation: A Primer"

## Implementation Details

### Rebalancing Logic
All strategies use consistent rebalancing detection:
- **Monthly**: `LastTradingDayOfMonth`
- **Quarterly**: `LastTradingDayOfMonth AND (currentMonth = 3 OR 6 OR 9 OR 12)`
- **Annual**: `LastTradingDayOfMonth AND currentMonth = 12`

### Key Features
- **Momentum Calculations**: Various lookback periods and weighting schemes
- **Risk Management**: Volatility and correlation adjustments
- **Crash Protection**: Canary universes and CPF calculations
- **Position Sizing**: Equal-weight or score-based allocations
- **Entry/Exit Logic**: Systematic rebalancing with entry restrictions

## Requirements

- **Platform**: MultiCharts Portfolio Trader
- **Data**: Daily total return data (dividend adjusted closes) for relevant asset classes
- **EL Collections DLL**: Required for List and Map functionality used in the strategies. Download from: https://www.multicharts.com/discussion/viewtopic.php?f=16&t=10094&p=48319#p48320
- **Indicators**: Custom functions for momentum, volatility, correlation calculations

## Usage

1. Import the strategy files into MultiCharts Portfolio Trader
2. Load the appropriate Signal Base file for your chosen strategy
3. Apply the corresponding Portfolio MM file for money management
4. Configure inputs according to strategy documentation
5. Use with daily total return data (dividend adjusted closes)
6. Backtest and validate on your historical data

## Disclaimer

These implementations are for educational and research purposes. Past performance does not guarantee future results. Always perform thorough backtesting and risk assessment before live trading. The authors are not responsible for any financial losses incurred through the use of these strategies.

## LICENSE / TERMS OF USE

This repository contains an educational implementation of algorithms originally developed by Jan Willem Keuning.

**Permission Status**: This code is published with the express written permission of the original author for educational and non-commercial sharing.

**Original Disclaimer & Restrictions**:

**Terms Of Use & Disclaimer - Not Investment Advice**

A. This code was created and is provided solely for informational and entertainment purposes. The information and material contained herein are the opinions of the author alone. Under no circumstances does this information nor the material contained herein constitute a recommendation to buy, to sell, or to hold any securities. The information and results are not intended to be and should not be considered investment advice or a recommendation to any user regarding their personal investment needs or economic circumstances. None of the content provided is intended as investment advice regarding any specific security, portfolio of securities, market strategy or investment transaction. In no event should the information and material contained herein be construed as an express of an implied promise, guarantee or implication by or from the author that the user will profit or that losses can or will be limited in any manner whatsoever. Past performance is not necessarily indicative of future results.

B. Users are cautioned that the author may hold positions in securities referenced herein and may hold positions inconsistent with those shown herein. These positions may or may not be disclosed herein. Investing in securities involves risks and persons considering an investment in securities should review all available public information and make decisions regarding any investment based upon their own particular economic needs and circumstances none of which are known to the author.

C. This code and the data and analysis contained herein is provided without any warranty, and no guarantees are offered as to the data contained herein, nor on any of the manipulations provided on that data, or the routines that are used to gather and manipulate the data.

D. This code is Copyright, 2015, 2016, 2017, 2018 by the author. For non-commercial usage, users are given permission to use and modify the code as long as they properly attribute the original source to the author as well as include this disclaimer. Express written permission from the author is required before any re-distributions or commercial use of the code contained herein.


**Note to Users**: You are free to study and fork this code for personal/educational use. For any commercial usage or further redistribution outside of GitHub, please refer to the original author's terms above.

