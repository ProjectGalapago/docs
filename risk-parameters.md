---
description: Risk Management Parameters
---

# Risk Parameters

Each asset in the Galapago Protocol has specific parameters that influences how they can be supplied and borrowed.

* Collateral Factor (CF) or Loan-to-Value (LTV) - What is the maximum amount that can be borrowed? It is represented as a % with numerator equal to Max Amount Borrowed/Value of Supplied Asset Max We will often refer to this value as Collateral Factor and abbreviate as CF.
* Liquidation Threshold (LT) - This represents the point when the asset would start to go through the liquidation process. It is represented as a % with numerator equal to Total Debt/Value of AssetTotal. The difference between the CF and Liquidation Threshold can be considered as the safety cushion for borrowers.
* Liquidation Bonus - The amount of additional collateral that liquidators receive / are discounted for purchasing assets on liquidation. Represented as percentage of the collateral purchased. This provides extra incentives for purchasing through liquidation.

### Collateral Factor <a href="#header-epal4-calculating-collateral-factor" id="header-epal4-calculating-collateral-factor"></a>

The maximum amount user can borrow is based on the weighted collateral factor--i.e. the value of assets supplied and their corresponding collateral values according to our Asset Risk parameters.

### Liquidation Threshold <a href="#header-6cc2r-liquidation-threshold" id="header-6cc2r-liquidation-threshold"></a>

For each wallet the Liquidation Threshold is calculate as the weighted average of the Liquidation Thresholds of the collateral assets and their value

### Summary Table

| Asset                  | Max Collateral Factor | Liquidation Threshold | Liquidation Bonus |
| ---------------------- | --------------------- | --------------------- | ----------------- |
| Algorand Bluechip NFTs | 40%                   | 70%                   | 8%                |
| ALGO                   | 65%                   | 65%                   | 8%                |
| USDC                   | 80%                   | 85%                   | 8%                |
| USDT                   | 80%                   | 85%                   | 8%                |
| gBTC                   | 70%                   | 80%                   | 8%                |
| gETH                   | 70%                   | 80%                   | 8%                |
| wBTC                   | 70%                   | 80%                   | 8%                |
| wETH                   | 70%                   | 80%                   | 8%                |

