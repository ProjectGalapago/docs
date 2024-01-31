# Lending Pool

Lending Pool is a crucial component of Project Galapago. It's a smart contract that aggregates users' deposits and manages users' borrowings for a specific asset. Each asset supported by Project Galapago has its unique LendingPool. The interaction between depositors and borrowers within a pool creates a dynamic ecosystem that regulates itself based on the utilization of the pool.

### Utilization Ratio

The utilization ratio ($$U$$) of a pool is defined as the ratio between the total borrowed amount and the total deposited amount in the pool:



$$
U=\frac {Total Borrowed Amount}  {Total Deposited Amount}
$$

The protocol leverages $$U$$ to maintain balance in the pool between deposits and loans. The utilization ratio plays a critical role in determining the interest rates for depositors and borrowers, and in ensuring that the pool remains sustainable and liquid.

* When $$U$$is high, it indicates that the pool has a high borrowing relative to the deposits. This situation reduces the available liquidity, which could pose problems if many depositors decide to withdraw their funds simultaneously. To mitigate this, the protocol increases the borrowing interest rate, and consequently, the deposit interest rate. This approach discourages new loans while incentivizing new deposits, thereby restoring liquidity to the pool.
* Conversely, when $$U$$ is low, it implies that there is excess liquidity in the pool. In this case, the protocol decreases the borrowing interest rate, and consequently, the deposit interest rate. This action incentivizes new borrowings and discourages further deposits, thereby ensuring the efficient utilization of the pool's assets.

This automatic adjustment of interest rates based on the utilization ratio ensures that the pool remains sustainable and attractive for both depositors and borrowers. It enables the protocol to balance the needs of depositors for returns on their deposits and borrowers for affordable interest rates on their loans. This system also ensures that the liquidity of the pool is always maintained, protecting the interests of all users of the protocol.
