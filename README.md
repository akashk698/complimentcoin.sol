# ComplimentCoin

## Project Description

ComplimentCoin is a blockchain-based token system designed for educational workshops and team-building activities. It allows participants to send digital "compliment coins" to each other along with personalized messages, creating a fun and interactive way to learn blockchain fundamentals while fostering positive communication.

### Key Features

- **Token System**: ERC-20 compatible token with 1 million total supply
- **User Registration**: Participants can register with display names
- **Compliment Messaging**: Send tokens with attached compliment messages
- **Transparent Transactions**: All compliments are permanently recorded on blockchain
- **Auto-Distribution**: New users automatically receive starter tokens

### Core Functions

1. **`registerUser(string _name)`** - Register with a display name and receive starter tokens
2. **`sendCompliment(address _to, uint256 _amount, string _message)`** - Send tokens with compliment message
3. **`getUserInfo(address _user)`** - Get user's balance, name, and registration status

### Project Structure

```
ComplimentCoin/
├── contracts/
│   └── ComplimentCoin.sol
├── README.md
└── package.json
```

### Getting Started

#### Prerequisites
- Node.js and npm
- MetaMask wallet
- Remix IDE or Hardhat development environment

#### Deployment Steps

1. **Using Remix IDE** (Recommended for beginners):
   - Open [Remix IDE](https://remix.ethereum.org)
   - Create new file: `ComplimentCoin.sol`
   - Copy and paste the contract code
   - Compile with Solidity ^0.8.19
   - Deploy to Polygon Mumbai testnet

2. **Using Hardhat** (Advanced):
   ```bash
   npm install --save-dev hardhat
   npx hardhat init
   # Copy contract to contracts/ folder
   npx hardhat compile
   npx hardhat run scripts/deploy.js --network mumbai
   ```

### Workshop Usage

#### Step 1: Setup
- Deploy contract to testnet
- Share contract address with participants
- Ensure everyone has MetaMask with test tokens

#### Step 2: Registration
```solidity
// Each participant calls:
registerUser("Your Name")
```

#### Step 3: Send Compliments
```solidity
// Send compliments to other participants:
sendCompliment(recipientAddress, 10, "Great presentation!")
```

#### Step 4: View Results
```solidity
// Check balances and user info:
getUserInfo(userAddress)
```

### Sample Interactions

```javascript
// Register user
await contract.registerUser("Alice");

// Send compliment
await contract.sendCompliment(
    "0x742d35Cc...", 
    ethers.utils.parseEther("5"), 
    "Thanks for helping me understand blockchain!"
);

// Get user info
const userInfo = await contract.getUserInfo("0x742d35Cc...");
console.log(`Balance: ${userInfo.balance}, Name: ${userInfo.userName}`);
```

### Events Emitted

- `UserRegistered(address user, string name)` - When user registers
- `ComplimentSent(address from, address to, uint256 amount, string message, uint256 timestamp)` - When compliment is sent
- `Transfer(address from, address to, uint256 value)` - Standard ERC-20 transfer event

### Educational Value

This project teaches:
- Smart contract development
- Token economics
- Blockchain immutability
- Event logging and transparency
- Wallet interactions
- Gas fees and transactions

### Security Features

- Input validation for names and messages
- Balance checking before transfers
- Owner-only functions for token distribution
- Address validation
- Overflow protection with Solidity ^0.8.0

### Future Enhancements

- Web interface for easier interaction
- Compliment categories and scoring
- Leaderboards and achievements
- Integration with social platforms
- Multi-language support

### License

MIT License - Feel free to use for educational purposes
<img width="1908" height="865" alt="image" src="https://github.com/user-attachments/assets/bac3bc00-2f36-450f-8f8d-ec2501e85aa5" />

### Support

For workshop support or questions, create an issue in the project repository or contact the workshop instructor.

---

*Built for blockchain education and positive team building! 🚀*
