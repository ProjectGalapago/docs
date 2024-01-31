# Portfolio Lending

The Portfolio Lending System is an innovative mechanism that transforms the traditional isolated margin pool into a cross-margin system. This system allows for a more efficient and flexible use of collateral, including both fungible tokens and NFTs. Each type of collateral is assigned a credit line, which can be used to provide loans across all types of collateral.

The system calculates a health coefficient for the entire portfolio of staked assets. As long as this coefficient remains above 1, no liquidation auction will be triggered for the staked NFTs.

### Limitations of Traditional Deposit Pool Design

In the traditional isolated margin pool design, the process of staking multiple assets and managing loans can be cumbersome. For instance, if a user wants to stake 5 blue chip NFTs to borrow ALGO for purchasing other NFTs, they would need to conduct 5 separate on-chain transactions and manage 5 different loan positions. This design not only increases operational complexity but also limits flexibility in managing liquidation risks.

### Advantages of Project Galapago's Portfolio Limit Design

Project Galapago's portfolio limit design addresses these issues by allowing users to deposit additional collateral (either NFTs or fungible tokens) to maintain a high health factor, thereby avoiding liquidation. Each type of collateral supported by Project Galapago is assigned a total value, which contributes to the overall health factor of the portfolio.

One of the key benefits of the cross-margin model is its ability to hedge risks. If a user's NFT portfolio contains assets with negative price correlations, it can mitigate the risk of liquidation due to sudden price changes in a single asset. This concept is similar to contract account positions in traditional trading. Through cross-margin, traders can use fewer funds to trade, achieve higher leverage ratios, and potentially earn higher returns in the market.
