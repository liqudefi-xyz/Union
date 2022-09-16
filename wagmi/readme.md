<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/wagmi-dev/.github/main/content/logo-dark.svg">
    <img alt="wagmi logo" src="https://raw.githubusercontent.com/wagmi-dev/.github/main/content/logo-light.svg" width="auto" height="60">
  </picture>
</p>

<p align="center">
  React Hooks for Ethereum
<p>

<div align="center">
  <a href="https://www.npmjs.com/package/wagmi">
    <img src="https://img.shields.io/npm/v/wagmi?colorA=21262d&colorB=161b22&style=flat" alt="Version">
  </a>
  <a href="https://www.npmjs.com/package/wagmi">
    <img src="https://img.shields.io/npm/dm/wagmi?colorA=21262d&colorB=161b22&style=flat" alt="Downloads per month">
  </a>
  <a href="https://bestofjs.org/projects/wagmi">
    <img src="https://img.shields.io/endpoint?colorA=21262d&colorB=161b22&style=flat&url=https://bestofjs-serverless.now.sh/api/project-badge?fullName=wagmi-dev%2Fwagmi%26since=daily" alt="Best of JS">
  </a>
</div>

<br>

> **Note**
>
> wagmi is participating in [Gitcoin Grant Round 15](https://wagmi.sh/gitcoin) until September 22. Contributions are matched with [Quadratic Funding](https://finematics.com/quadratic-funding-explained/) (e.g. $1 turns into $27). If you find wagmi useful, please consider supporting development [here](https://wagmi.sh/gitcoin). Thank you 🙏

## Features

- 🚀 20+ hooks for working with wallets, ENS, contracts, transactions, signing, etc.
- 💼 Built-in wallet connectors for MetaMask, WalletConnect, Coinbase Wallet, and Injected
- 👟 Caching, request deduplication, multicall, batching, and persistence
- 🌀 Auto-refresh data on wallet, block, and network changes
- 🦄 TypeScript ready
- 🌳 Test suite running against forked Ethereum network

...and a lot more.

## Documentation

For full documentation and examples, visit [wagmi.sh](https://wagmi.sh).

## Installation

Install wagmi and its ethers peer dependency.

```bash
npm install wagmi ethers
```

## Quick Start

Connect a wallet in under 60 seconds. LFG.

```tsx
import { WagmiConfig, createClient } from 'wagmi'
import { getDefaultProvider } from 'ethers'

const client = createClient({
  autoConnect: true,
  provider: getDefaultProvider(),
})

function App() {
  return (
    <WagmiConfig client={client}>
      <Profile />
    </WagmiConfig>
  )
}
```

```tsx
import { useAccount, useConnect, useDisconnect } from 'wagmi'
import { InjectedConnector } from 'wagmi/connectors/injected'

function Profile() {
  const { address } = useAccount()
  const { connect } = useConnect({
    connector: new InjectedConnector(),
  })
  const { disconnect } = useDisconnect()

  if (address)
    return (
      <div>
        Connected to {address}
        <button onClick={() => disconnect()}>Disconnect</button>
      </div>
    )
  return <button onClick={() => connect()}>Connect Wallet</button>
}
```

In this example, we create a wagmi `Client` and pass it to the `WagmiConfig` React Context. The client is set up to use the ethers Default Provider and automatically connect to previously connected wallets.

Next, we use the `useConnect` hook to connect an injected wallet (e.g. MetaMask) to the app. Finally, we show the connected account's address with `useAccount` and allow them to disconnect with `useDisconnect`.

We've only scratched the surface for what you can do with wagmi!

—

Check out [ConnectKit](https://docs.family.co/connectkit?utm_source=wagmi-dev) to get started with pre-built interface on top of wagmi for managing wallet connections.

## Community

Check out the following places for more wagmi-related content:

- Join the [discussions on GitHub](https://github.com/wagmi-dev/wagmi/discussions)
- Follow [@wagmi_sh](https://twitter.com/wagmi_sh) on Twitter for project updates
- Share [your project/organization](https://github.com/wagmi-dev/wagmi/discussions/201) using wagmi
- Browse the [awesome-wagmi](https://github.com/wagmi-dev/awesome-wagmi) list of awesome projects and resources

## Support

If you find wagmi useful, please consider supporting development. Thank you 🙏

- [GitHub Sponsors](https://github.com/sponsors/wagmi-dev?metadata_campaign=gh_readme_support)
- [Gitcoin Grant](https://gitcoin.co/grants/4493/wagmi-react-hooks-library-for-ethereum)
- [wagmi-dev.eth](https://etherscan.io/enslookup-search?search=wagmi-dev.eth)

## Sponsors

<a href="https://twitter.com/family">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/wagmi-dev/.github/main/content/sponsors/family-dark.svg">
    <img alt="family logo" src="https://raw.githubusercontent.com/wagmi-dev/.github/main/content/sponsors/family-light.svg" width="auto" height="50">
  </picture>
</a>
<a href="https://twitter.com/context">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/wagmi-dev/.github/main/content/sponsors/context-dark.svg">
    <img alt="context logo" src="https://raw.githubusercontent.com/wagmi-dev/.github/main/content/sponsors/context-light.svg" width="auto" height="50">
  </picture>
</a>

## Contributing

If you're interested in contributing, please read the [contributing docs](/.github/CONTRIBUTING.md) **before submitting a pull request**.

## Authors

- awkweb.eth ([@awkweb](https://twitter.com/awkweb)) – [Mirror](https://mirror.xyz)
- moxey.eth ([@jakemoxey](https://twitter.com/jakemoxey)) – [Rainbow](https://rainbow.me)

Thanks to julianhutton.eth ([@julianjhutton](https://twitter.com/julianjhutton)) for providing the awesome logo!

## License

[WAGMIT](/LICENSE) License

<br />

<a href="https://vercel.com/?utm_source=wagmi-dev&utm_campaign=oss">
  <img src="https://www.datocms-assets.com/31049/1618983297-powered-by-vercel.svg" alt="Powered by Vercel" height="35">
</a>
