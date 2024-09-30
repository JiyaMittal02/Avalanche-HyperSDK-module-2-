

# Customized Subnet Using HyperSDK

This project is designed to facilitate the creation, management, and interaction of tokens within a custom virtual machine environment using Avalanche's HyperSDK.

## Features
- **Token Creation**: Effortlessly create new tokens within your custom subnet.
- **Token Management**: Manage tokens easily, including handling transfers and checking balances.
- **Interoperability**: Designed for seamless integration with other virtual machine environments and subnets.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Metacrafters/tokenvm.git
   cd tokenvm
   ```

2. Set the constants in `consts/consts.go`.

3. Add the necessary code in `registry/registry.go`.

4. Launch the subnet using the following command:
   ```bash
   ./scripts/run.sh
   ```

   By default, this allocates all funds on network 5. Next, build the project with:
   ```bash
   ./scripts/build.sh
   ```
   This command compiles the CLI and places it in `./build/token-cli`.

## Mint and Trade

### Step 1: Create Your Asset
Create your custom asset by running:
```bash
./build/token-cli action create-asset
```
The output will display the new asset's details:
```
database: .token-cli
address: token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp
chainID: Em2pZtHr7rDCzii43an2bBi1M2mTFyLN33QP1Xfjy7BcWtaH9
metadata: MarioCoin
continue (y/n): y
✅ txID: 27grFs9vE2YP9kwLM5hQJGLDvqEY9ii71zzdoRHNGC4Appavug
```

### Step 2: Mint Your Asset
Mint tokens by running:
```bash
./build/token-cli action mint-asset
```
The output will confirm the minting of tokens:
```
database: .token-cli
address: token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp
assetID: 27grFs9vE2YP9kwLM5hQJGLDvqEY9ii71zzdoRHNGC4Appavug
amount: 10000
continue (y/n): y
✅ txID: X1E5CVFgFFgniFyWcj5wweGg66TyzjK2bMWWTzFwJcwFYkF72
```

### Step 3: View Your Balance
Check the balance by running:
```bash
./build/token-cli key balance
```

### Step 4: Create an Order
Put an order on-chain to trade tokens:
```bash
./build/token-cli action create-order
```

### Step 5: Fill Part of the Order
Fill an order on-chain:
```bash
./build/token-cli action fill-order
```

### Step 6: Close Order
Cancel the order by running:
```bash
./build/token-cli action close-order
```

## Transfer Assets to Another Subnet

You can transfer assets between two subnets with:
```bash
./build/token-cli action export
```
Follow the prompts to complete the transfer and switch the default chain if needed.
## Author
Jiya Mittal
