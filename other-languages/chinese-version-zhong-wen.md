# Chinese Version 中文

## 项目简述

Project Galapago 是一个集成“点对点”及“点对池”NFT抵押借贷协议，主要服务于蓝筹NFT持有者。点对池贷款人（点）可通过在协议池（池）中抵押蓝筹NFT快速贷出资金池内加密幣，存款人（点）向资金池（池）提供加密幣，获取以加密幣计价的利息，并且借贷双方均会获得$PAGO挖矿奖励。

除了主要点对池**借贷业务**外，Project Galapago还提供了内置的**交易市场**，支持“点对点”借贷（Peer-to-Peer）功能等。

Project Galapago以蓝筹NFT资产为抵押物借贷加密幣为主要业务，其他业务有Project Galapago上内置的交易市场，支持用户借贷的同时，也支持用户创建和购买NFT。基于以上的业务，协议主要收入来源是抵押借贷产生的息差收入，其他收入还有交易市场带来的交易费用收入（2%费率）和购买手续费收入（1%费率）。\


## NFT借贷业务

### **抵押物估值方法**

NFT定价决定了可贷款出资金的基数。Galapago为NFT抵押物的定价通过内置价格计算器实现，将链下的OpenSea和LooksRare等NFT交易市場地板价进行一定清洗处理后，通过预言机喂价给协议，协议在链上采用TWAP（时间加权计算法，Time-Weighted Average Price）计算得出NFT的价值。

采用该种方法的定价使得Project Galapago上对NFT的定价不会过低，也可以降低协议地板价被操纵的风险，从而避免NFT清算被轻易触发，**具有效率高、成本低、抗操纵的优势。**

### **借贷利率 Interest Rate Model**

Project Galapago的借贷利率随池内资金利用率浮动，资金利率用率高时，借贷利率上升刺激存款、抑制贷款，当资金利用率高于45%时，利率上升速率加快，资金利用率低时，借贷利率下降。

协议池资金充足性及抵押物资产质量决定了点对池协议的健康程度，因此Project Galapago的浮动利率机制作为一种自动调节机制，维持协议平衡。

### **清算机制**

Project Galapago协议的清算机制为公开拍卖形式。清算线（Liquidation Threshold）为80%，即当某一负债总额超过协议地板价80%时，其贷款的健康因子低于1，抵押物会进入清算流程。当第一个竞拍者出现后，会启动24小时拍卖流程。Project Galapago采用英式拍卖的方式，起拍价需大于等于贷款的负债本息和，后续竞拍价格需至少按总负债金额1%递增，若贷款人在24小时拍卖期间偿付至少50%负债金额，可以赎回抵押物，但也需要向首个竞拍者支付清算补偿金作为奖励，奖金为300 USDT和5%负债金额之间的较高值；若24小时内贷款人没有进行偿还，则最后竞拍者，也是出价最高者拍得NFT。

#### 健康因子计算公式

健康因子 = （地板价 x 清算线 ）/ 负债总额；Health Factor = (Floor Price \* Liquidation Threshold) / Debt with Interests

## **NFT交易市场业务**

Project Galapago内置的NFT交易市场，主要为贷款人和NFT用户提供更多服务，支持NFT用家在借贷的同时创建，购买和销售NFT。
