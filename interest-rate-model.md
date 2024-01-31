# Interest Rate Model

The interest rates charged to borrowers in Project Galapago are not static; they are dynamic and depend on the pool's Utilization Rate ($$U$$). This dynamic interest model is designed to promote liquidity within the pool.

When there is an abundance of capital (low $$U$$), borrowers pay less interest to incentivize borrowings. However, when capital becomes scarce (high $$U$$), interest rates increase to encourage more deposits and prompt borrowers to repay their loans, thereby replenishing the pool's liquidity.

The mechanism also accounts for liquidity risk. As $$U$$ approaches 100%, the liquidity risk increases. To manage this risk, the protocol implements an inflection point ($$Uoptimal​$$), beyond which the interest rate slope increases sharply. This inflection point is a crucial part of the interest model, triggering a rapid rise in interest rates when $$U$$ exceeds $$Uoptimal​$$ and helping to restore liquidity quickly.

The interest rate model can be represented as:

$$if \hspace{1mm} U < U_{optimal}: \hspace{1cm} R_t = R_0 + \frac{U_t}{U_{optimal}} R_{slope1}$$

$$if \hspace{1mm} U \geq U_{optimal}: \hspace{1cm} R_t = R_0 + R_{slope1} + \frac{U_t-U_{optimal}}{1-U_{optimal}}R_{slope2}$$

where $$R_{slope1}, R_{slope2}$$ and $$R_0$$ are parameters that define the slopes and intercepts of the interest rate model, and $$R_t$$ is the resulting interest rate.

The actual annual percentage yield (APY) can be calculated as:

$$
ActualAPY=(1+ \frac  {TheoreticalAPY} {secsperyear})^{secsperyear}−1
$$

This model ensures that the interest rates adapt to the current liquidity conditions, promoting the sustainability of the pool and providing fair returns for depositors and reasonable rates for borrowers. It ensures that the pool remains liquid, reduces risks, and balances the needs of all users of the protocol.
