---
description: Monitor and Manage Protocol Financial Risk
---

# Loan Health Factor & Liquidation

### Loan Health Factor

The liquidation mechanism in Project Galapago is designed to maintain the protocol's financial health. It is activated when a user's Loan Health Factor falls below 1, indicating that the value of their collateral is insufficient to cover their loan. The Loan Health Factor is calculated by dividing the floor price of the collateral (multiplied by the liquidation threshold) by the total value of the loan. When a user's Loan Health Factor falls equal to or below 1, the loan is at risk of being liquidated. The protocol then alerts the Health Factor list, and anyone can trigger an auction against the collateral.

### Fungible Token Liquidations

When the Health Factor for fungible tokens or NFTs falls below 1, assets will be liquidated. The protocol prioritizes liquidating fungible tokens (ALGO and USDC) before NFTs due to their greater liquidity. Liquidators can claim ALGO and USDC tokens before NFTs. These non-NFT collaterals will be used to pay down the overall debt (total borrow + interest owed).

### NFT Liquidation Auction <a href="#header-2tgih-nft-liquidation-auction" id="header-2tgih-nft-liquidation-auction"></a>

An NFT auction will be initiated when the health factor is equal to or below 1. More specifically, the loan will be liquidated when the debt value is worth liquidation threshold (e.g. 80%) of the collateral value.

* An open-outcry ascending dynamic auction system
* The system opens the auction with a starting price. The starting price will be greater than the total accumulated debt.
* If the borrowers repay the loan in 8 hours, he/she will pay a fine to the first bidder.
* The fine will be maximum of (5% debt or 1500 ALGO).

### Bidder <a href="#header-9f1qa-bidder" id="header-9f1qa-bidder"></a>

* Anyone can take part in an auction.
* The bid must be:1) no less than the starting price; 2) higher than the previous bid plus 1% debt.
* The first bidder will receive at least 1500 ALGO paid by the borrower as the penalty if the borrower repays within 8 hours.&#x20;
* The highest bidder will get the collateral if the borrower doesn't repay the loan.
* The bidder needs to deposit ALGO to bid.
* The deposited ALGO will automatically be refunded when his/her bid is not the highest bid.

### Borrower <a href="#header-64oaq-borrower" id="header-64oaq-borrower"></a>

* The borrower will have a liquidation protection period to repay the loan.
* If the borrower repays 50% of the debt within 8 hours, he/she will pay a fine of a maximum(5% of the debt, 1500 ALGO) to the first bidder.
* If the collateral is sold in auction for greater than the loan amount, the excess will belong to the borrower.
