---
description: Let's start deploying your own NFT Staking DAPP together
---

# 🚀 Get Started

## Development environment

Install all required dependencies for Solana / Anchor development environment.

### Install Rust

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
rustup component add rustfmt
```

On Linux systems you may need to install additional dependencies. On Ubuntu,

```
sudo apt-get install -y pkg-config build-essential python3-pip jq
```

### Install Solana

Directions can be found [here](https://docs.solana.com/cli/install-solana-cli-tools#use-solanas-install-tool).

### Install Yarn <a href="#install-yarn" id="install-yarn"></a>

[Yarn (opens new window)](https://yarnpkg.com/)is recommended for JavaScript package management.

```
npm install -g yarn
```

### Install Anchor

[Anchor](https://github.com/project-serum/anchor) is used for development, and it's recommended workflow is used here. To get started, see the [guide](https://project-serum.github.io/anchor/getting-started/introduction.html).



Now verify the CLI is installed properly.

```
anchor --version
```

## Minimum version requirements <a href="#minimum-version-requirements" id="minimum-version-requirements"></a>

| Build tool | Version |
| ---------- | ------- |
| Node.js    | v11.0.0 |
