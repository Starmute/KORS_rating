# KORS - Knife Objective Rating Standard

After the Weiss Ratings fiasco, I realized many people wanted an actual, objective rating system that made sense. KORS is designed to be exactly this - and designed so that anyone can verify, modify and contribute to. In effect, KORS is a cryptocurrency rating system created to follow the open-source vision.

THIS PROJECT IS ***NOT*** COMPLETE. MOST OF THE METRICS ARE NOT EVEN DONE YET. DON'T USE THESE RATINGS FOR ANYTHING IMPORTANT.

Within KORS, there are two types of ratings: weighted and unweighted. Weighted multiplies each category by a weight value according to its importance, whereas unweighted keeps all categories equal. No rating category may exceed the range [0,10] at any time (excepting penalties), and a mathematically calculated value should be restricted to this range if it exceeds it.

Beyond these, we also propose quantitative and qualitative categories. One can choose to exclude either, as the qualitative ratings are far more subjective, but the quantitative ratings may not be as relevant to cryptocurrency markets. Rather than being decided by a central authority, KORS qualitative ratings should be decided and interpreted based on consensus.

KORS is designed such that a failure in any one category won't harm the others; a truly holistic rating system. Without further ado, here is the definition of the standard:

# Commits per month

Code activity should be considered critical to project success. It is the definition of whether a project is alive or dead. We assign it a rating of 3 in the weighted system.

Take the median number of commits per month over the past three months, divide by 2, and subtract 5 (`R=(N/2)-5`). Don’t round. Range is [0, 10], unless commits are zero, in which an additional five points will be deducted.

# Number of contributors

The number of contributors to the code is paramount not only for the integrity of code but for decentralization as well. Therefore, we assign it a rating of 4 in the weighted system.

Consider the number of code contributors since the project’s inception. This ***DOES NOT*** include code from a coin from which the project in question was forked. Divide this number by four and subtract five. Don’t round. Range is [0, 10]. There is an additional two point penalty if no code is public.

# Development type

Who is behind the project? This in itself can say a great deal - a project led and created only by anonymous people surely is not as trustworthy as one with the backing of known individuals. On the other hand, a corporate-backed cryptocurrency has centralization issues. Given the importance of this category, we assign it a weight of 5 in the weighted system.

Corporation: 0 (ex. Ripple, Zcash)

Centralized foundation: 3 (ex. Ethereum, IOTA)

Corporate-assisted development: 6 (Bitmain/BCH, Blockstream/BTC)

Community-based development: 10 (ex. Monero)

# Completeness

Completeness is a temporary state, and often not too relevant to the future of the coin, but it can impact perception and utility of the coin in the present. Therefore we assign it a weight of 4 in the weighted system.

There are four possible scores for this metric:

- Temporary ERC20 (ex. Tron): 0

- Permanent ERC20 (ex. Crypto20): 2.5

- Unfinished (example: Cardano, as despite having a working token, its smart contract platform is not yet in operation): 5

- Working (ex. Bitcoin, Litecoin): 10

# Tx/s scaling

Scalability is a highly relevant issue for the future of blockchain technology. We rate it a 6 in the weighted system.

Consider the theoretical maximum transactions per second supported by the network on the base layer. The following scores are allotted to each range:

5-15: 0

15-60: 1

60-240: 2.5

240-1000: 5

1000+: 10

A coin with a dynamic blocksize, such as Monero, shall receive a score of 6 for this metric.

# Prunability

Prunability is the ability to safely remove blockchain history while retaining a full node. It's quite important, but often reserved for future applications, so we assign it a weight of 2 in the weighted system.

There are a few different varieties, which receive different scores:

0 points: None

5 points - “Snapshot” - Destroy the entire chain once every X days and start anew, setting each account to its current balance. This mechanism is used by IOTA.

10 points - Passive pruning; the chain is pruned as it is constructed. An example of this would be Grin, or Nano once its universal blocks are implemented.

# Node decentralization

Consider the number of currently active nodes for this coin. Divide by 200 and subtract two. Round to the nearest unit. Range is [0, 10].

If there is a central trusted verifier, the score shall be zero regardless of the number of nodes.

# Transaction fees

Consider the median transaction fee in United States dollars. Multiply by ten and subtract this value from 10. Exception: For median fees less than one US cent, the score is 7.5, *UNLESS* a transaction spam prevention mechanism, such as required PoW-per-transaction, is employed, in which case the score is 10. Range is [0, 10]. (Note: might change this to fee-per-kB related measure.)

# Privacy capabilities

Consider the type of privacy, if any, that the coin employs.

No privacy: 0 (ex. Bitcoin)

Optional privacy hiding *some* transaction details: 2.5 (ex. Dash, Zcoin)

Optional privacy hiding *all* transaction details: 7.5 (ex. Zcash)

Mandatory privacy hiding *some* transaction details: 7.5 (ex. Bytecoin, Electroneum)

Mandatory privacy hiding *all* transaction details: 10 (ex. Monero)

# Launch type

Consider the method by which the coin was launched. The following methods receive the corresponding scores:

ICO, not sold out: 0

ICO, sold out: 2

Partial premine + subsequent mining: 4 (ex. Bytecoin)

Chain fork / Airdrop: 6

Open mining / Initial faucet: 10

# Scripting capabilities

Scripting is an important aspect of cryptocurrency, and is critical to features such as atomic swaps, so we'll assign it a weight of 3 in the weighted system. The following scores are awarded:

None: 0

Bare: 2.5 (MimbleWimble scriptless scripts / Multisig only)

Limited: 5 (Bitcoin Script)

Turing complete: 10 (Ethereum)

An incomplete platform, such as EOS or Cardano, that *plans* to have scripting capability, will receive a score of 0 until its scripting capabilities are activated.

Still working on the rest of the metrics but that’s a nice start.
