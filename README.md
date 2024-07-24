# Swisstronik Tesnet Techinal Task 3 (Mint a ERC-721 Token)

## Steps

### 1. Clone Repository

```bash
git clone https://github.com/Mnuralim/swisstronik-erc721-mint-token.git
```

```
cd swisstronik-erc721-mint-token
```

### 2. Install Dependency

```bash
npm install
```

### 3. Set .env File

Create a .env file in the root directory of the project:

```bash
PRIVATE_KEY="your private key"
```

### 4. Update Smart Contract (Skipp if you won't modify NFT name)

If you want to modify the NFT name or symbol, follow these steps:

- Navigate to the contracts folder
- Open the Nft.sol file
- Modify the token name and symbol as desired

```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC721/ERC721.sol";

contract TestNFT is ERC721 {
    uint256 private _currentTokenId = 0;

    event NFTMinted(address recipient, uint256 tokenId);

    constructor() ERC721("JomokNFT", "JMKNFT") {}

    function mintNFT(address recipient) public returns (uint256) {
        _currentTokenId += 1;
        uint256 newItemId = _currentTokenId;
        _mint(recipient, newItemId);

        emit NFTMinted(recipient, newItemId);

        return newItemId;
    }

    function burnNFT(uint256 tokenId) public {
        _burn(tokenId);
    }
}

```

### 5. Compile the Smart Contract

```bash
npm run compile
```

### 6. Deploy the Smart Contract

```bash
npm run deploy
```

### 7. Mint a Token

```bash
npm run mint
```

### 8. Finsihed

- Open deployed-address.ts in the utils folder and copy the address
- Paste the address into the testnet dashboard
- Open tx-hash.txt in the utils folder and copy the transaction hash link
- Paste the transaction hash link into the testnet dashboard
- Push this project to your GitHub and paste your repository link in the testnet dashboard

