## rDEV42

I read Solidity that changed recently and check whether it still works with what it talks to.

Most of what I find isn't a clever exploit. A protocol upgrades a dependency (an Aave pool, a LayerZero endpoint, a vault implementation) and something it calls stops existing, or a storage slot moves, or a cross-chain setting no longer matches the other side. Audits often predate that change. That gap is where I look.

### What I do

- Review integrations after upgrades: removed functions, changed return values, storage layout between implementations, peer and limit configuration across chains.
- Small and mid-size DeFi (roughly $2M to $30M TVL): vaults, bridges, restaking and yield wrappers.
- Verify on a mainnet fork before reporting anything. If I can't reproduce it, I don't send it.

### Tooling

I wrote my own scripts for this work. One of them is public:

- [selector-drift](https://github.com/r-DEV42/selector-drift): finds calls to functions that a dependency no longer has after an upgrade.

The rest (storage layout comparison between implementations, upgrade monitoring) I keep for my own reviews.

### Disclosures

Reports go to the teams privately, through GitHub security advisories or email. Some are still open. I'll list them here once they're fixed and the teams agree.

### Contact

Open to scoped reviews of upgrades and integrations.


X: [@rDEV4224](https://x.com/rDEV4224)
