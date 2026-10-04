<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./slate-dark.svg">
  <img src="./slate-light.svg" alt="Slate" height="44">
</picture>

**Prices for the 159 Robinhood stock tokens that Chainlink doesn't cover.** Live on Robinhood Chain mainnet for 20 of them so far, CRWD first.

**The gap.** Robinhood Chain has 194 stock tokens and Chainlink publishes feeds for 35. Of the 194, 45 carry an ERC-8056 multiplier other than 1, and 32 of those have no feed. Read at mainnet block 79,510,181 (4 Oct 2026), with Chainlink's feed directory read the same day. Rebuild the numbers: [`multiplier-census.mjs`](https://github.com/Slate-Protocol/slate/blob/main/dashboard/scripts/multiplier-census.mjs).

**The idea.** A Slate feed is a signed share price × the multiplier in force when that price was observed, served through Chainlink's `AggregatorV3Interface`, so anything that reads Chainlink reads Slate unchanged. Around a split it refuses with a named status rather than guess.

**Example.** CRWD has no Chainlink feed and a 4:1 split behind it. Its first signed mainnet price: $268.105 × 4.000 = **$1,072.42** ([transaction](https://robinhoodchain.blockscout.com/tx/0x0d8a2bde33c69e0ae8f931314a6ebe3dcebf29a1860c268d0ffdb3e30e9cccda)).

```sh
npm install @slate-protocol/contracts
```

**Status.** Live on Robinhood Chain mainnet; all 29 mainnet contracts verified on Sourcify. **Unaudited.** Our own invariant tests found a gap in the deployed feed that we have not yet deployed a fix for: [what it is, what it could cost, and the fix](https://docs.slate.0xo.in/security).

[slate.0xo.in](https://slate.0xo.in) · [app.slate.0xo.in](https://app.slate.0xo.in) · [docs.slate.0xo.in](https://docs.slate.0xo.in) · [x.com/Slateonchain](https://x.com/Slateonchain)

**Repositories**

- [slate](https://github.com/Slate-Protocol/slate): everything that runs. Contracts and tests, the signer and publisher, the dashboard, the docs and the npm package.
- slate-site (private): the landing page at slate.0xo.in, private only because it is built on a licensed template.
- [.github](https://github.com/Slate-Protocol/.github): this page.
