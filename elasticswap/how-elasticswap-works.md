---
description: >-
  Rather than jumping straight to math, and our supporters giving up on the docs
  altogether, here is a "simplified" example of how ElasticSwap works vs.
  Sushi/Uniswap V2.
---

# How ElasticSwap Works

ElasticSwap adapts to the elastic supply changes without the need for someone to call a function on the pool itself after a change (rebase) happens. This makes it less likely that value accrued through a rebase will be lost and helps to avoid excessive impermanent loss. Uniswap v2 / Sushi, for instance, requires the calling of `sync()` on the pool every time a rebase occurs in order to update token balances. ElasticSwap puts the excess tokens off to the side so the ratio of each token remains constant during a rebase event.

In the below examples, decay refers to excess value that is not being utilized for the purposes of trading.

### Examples with USDC / AMPL pools (10% positive rebase):

#### &#x20;Uniswap V2 / Sushi

Pool balances before rebase:&#x20;

10000 AMPL / 10000 USDC, 1 AMPL costs 1.0001 (repeating) USDC&#x20;

Pool balances after rebase:&#x20;

11000 AMPL / 10000 USDC, 1 AMPL costs \~0.90917356 USDC

#### ElasticSwap

Pool balances before rebase:&#x20;

10000 (0 decay) AMPL / 10000 (0 decay) USDC, 1 AMPL costs 1.0001 (repeating)&#x20;

USDC Pool balances after rebase:&#x20;

10000 (1000 decay) AMPL / 10000 (0 decay) USDC, 1 AMPL costs 1.0001 (repeating) USDC

### Examples with USDC / AMPL pools (10% negative rebase):&#x20;

#### Uniswap V2 / Sushi

Pool balances before rebase:&#x20;

10000 AMPL / 10000 USDC, 1 AMPL costs 1.0001 (repeating) USDC&#x20;

Pool balances after rebase:&#x20;

9000 AMPL / 10000 USDC, 1 AMPL costs \~1.11123458 USDC

#### ElasticSwap

Pool balances before rebase:&#x20;

10000 (0 decay) AMPL / 10000 (0 decay) USDC, 1 AMPL costs 1.0001 (repeating) USDC&#x20;

Pool balances after rebase:&#x20;

9000 (0 decay) AMPL / 10000 (1000 decay) USDC, 1 AMPL costs 1,0001111235 USDC&#x20;

With ElasticSwap the decay is settled when the next LP enters. Let's say the LP is willing to enter with 2000 AMPL and 2000 USDC. In the first (10% positive rebase) example, the LP would actually enter with 1000 AMPL and 2000 USDC, resolving the decay. In the second example (10% negative rebase) they would enter with 2000 AMPL and 1000 USDC. When LP tokens are redeemed, the LP receives their share of the entire balances including decay. In the first example, redeeming 10% of the total LP tokens would result in 1100 AMPL and 1000 USDC. In the second, 900 AMPL and 1000 USDC. These redemption amounts would be the same as with Uniswap V2 / Sushi.
