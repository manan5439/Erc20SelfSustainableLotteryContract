# Decentralized Lottery Smart Contract

This Ethereum smart contract facilitates a decentralized lottery system. Participants can enter the lottery using ERC20 tokens, and the system automatically selects winners after each 10-minute interval. If the interval exceeds, the next participant to buy a ticket will trigger the lottery result announcement for the previous session and will be rewarded for this action.

## Key Features

- **Support for Multiple ERC20 Tokens**: Participants can enter the lottery with any ERC20 token supported by the contract.
- **Automated and Timed Draws**: Lottery draws are intended to occur every 10 minutes. If a draw is overdue, the next ticket purchase triggers the draw and rewards the purchaser for announcing the result.
- **Social Cause Contribution**: 50% of the lottery proceeds are dedicated to social causes.
- **Rewards for Participants**: Besides the lottery winnings, participants receive native tokens as a bonus for their participation. Additionally, the individual who triggers an overdue lottery result announcement is rewarded, acknowledging the gas cost associated with this task.

## Setup and Deployment

### Prerequisites

- Node.js and npm must be installed.
- Truffle Framework should be set up for deploying and managing smart contracts.
- An Ethereum wallet with some ETH for contract deployment and interaction.

### Deployment Steps

1. Clone the repository and navigate into the project directory:

   ```bash
   git clone <repository_url>
   cd <project_directory>

2. Install required npm dependencies:
   ```bash
   npm install
   
3. Create a .env file in the project root. Add your Ethereum wallet's private key and your Infura API key: 
   ```bash
   PRIVATE_KEY=<your_private_key>
   INFURA_API_KEY=<your_infura_api_key>

4. Compile the smart contracts:
   ```bash
   truffle compile

5. Compile the smart contracts:
   ```bash
   truffle migrate --network rinkeby

## How to Use

### Buying Lottery Tickets

Approve the smart contract to spend the ERC20 tokens you want to use for buying lottery tickets. Then, call `buyLottery(address token)` to purchase your ticket. If the current lottery time has exceeded 10 minutes, this action will also trigger the announcement of the previous lottery's results, and you will receive a reward for this.

### Viewing Lottery Information

You can call `getDetails(address token, uint256 lotteryNumber)` to retrieve details about any lottery session, such as the total fund, number of participants, and the start time.

### Utility Functions

- `getTotalTokenCount()`: Returns the total number of distinct tokens used in the lotteries.
- `getToken(uint256 number)`: Retrieves the address of a specific token by its index.
- `getCurrentLotteryNumber(address token)`: Fetches the latest lottery session number for a given token.

## Contributing

Contributions to improve the contract or its documentation are welcome. Please feel free to open issues, submit pull requests, or suggest features.

## License

This project is licensed under the MIT License - see the LICENSE file for details.



