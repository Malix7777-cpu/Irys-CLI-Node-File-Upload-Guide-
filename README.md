# Irys-CLI-Node-File-Upload-Guide-

## 📔 Introduction

The **Irys CLI** is a command-line tool for interacting with
[Irys](https://irys.xyz/), a decentralized **data availability layer**
that enables you to:\
- Upload files, JSON, metadata, etc.\
- Manage on-chain/off-chain data\
- Get permanent storage guarantees

------------------------------------------------------------------------

## 💻 System Requirements

-   Works on **minimal VPS/PC**\
-   Recommended:
    -   Ubuntu 20.04+ / MacOS\
    -   **1 vCPU, 1 GB RAM, 10 GB Disk**

------------------------------------------------------------------------

## 🔧 Install Dependencies

``` bash
sudo apt-get update && sudo apt-get upgrade -y
```

``` bash
sudo apt install curl iptables build-essential git wget lz4 jq make protobuf-compiler cmake gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip screen ufw -y
```

------------------------------------------------------------------------

## ⚡ Install Node.js & NPM

**For Linux:**

``` bash
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - && sudo apt install -y nodejs
```

**For Mac:**

``` bash
brew install node
```

✅ Verify installation:

``` bash
node -v
npm -v
```

------------------------------------------------------------------------

## 📥 Install Irys CLI

``` bash
sudo npm i -g @irys/cli
```

Verify:

``` bash
irys
```

------------------------------------------------------------------------

## ⚙️ CLI Parameters

  -------------------------------------------------------------------------------------
  Option             Description
  ------------------ ------------------------------------------------------------------
  `-n`               Network to check: `mainnet` or `devnet` (default: mainnet).

  `-t`               [Token](https://docs.irys.xyz/build/d/features/supported-tokens)
                     to use.

  `-w`               Your **private key** (without `0x`).

  `--tags`           Tags to include → `<file_name> <file_format>`.

  `--provider-url`   RPC URL to use. Get from [Chainlist](https://chainlist.org/).
  -------------------------------------------------------------------------------------

------------------------------------------------------------------------

## 💰 Fund Your Wallet (Testnet/Devnet)

``` bash
irys fund 1000000   -n devnet   -t ethereum   -w PRIVATE_KEY   --provider-url RPC_URL
```

-   🔑 Replace **`PRIVATE_KEY`** with your wallet private key (without
    `0x`)\
-   🌍 Replace **`RPC_URL`** with your RPC (e.g.,
    https://sepolia.drpc.org)\
-   💧 Get faucet: [Ethereum Sepolia
    Faucet](https://sepolia-faucet.pk910.de/)

⚠️ Fund amount is in **wei**

------------------------------------------------------------------------

## 💳 Check Balance

``` bash
irys balance WALLET_ADDRESS   -t ethereum   -n devnet   --provider-url RPC_URL
```

-   Replace `WALLET_ADDRESS` with your wallet address\
-   Replace `RPC_URL` with your selected RPC

------------------------------------------------------------------------

## 📤 Upload a File

``` bash
irys upload FILE_NAME   -n devnet   -t ethereum   -w PRIVATE_KEY   --tags FILE_NAME FILE_FORMAT   --provider-url RPC_URL
```

-   Replace `FILE_NAME` → your actual file name\
-   Replace `FILE_FORMAT` → e.g., PNG, JPG, JSON\
-   Replace `PRIVATE_KEY` → your wallet key\
-   Replace `RPC_URL` → your selected RPC

------------------------------------------------------------------------

## ✅ Quick Recap

1.  Install dependencies & Node.js\
2.  Install Irys CLI\
3.  Fund your wallet with test tokens\
4.  Check your balance\
5.  Upload your file 🎉

------------------------------------------------------------------------

✨ That's it! You're now ready to use **Irys CLI** for decentralized
storage.
