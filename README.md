# PredictionBot - Automated Trading Bot for PancakeSwap & CandleGenie

A sophisticated TypeScript-based trading bot that automatically places bets on BNB-USD price predictions across PancakeSwap and CandleGenie platforms. The bot uses intelligent strategies to maximize winning probability by analyzing market sentiment and betting patterns.

## 🚀 Features

- **Dual Platform Support**: Works with both PancakeSwap Prediction V2 and CandleGenie Prediction V3
- **Smart Betting Strategies**: 
  - **Against Strategy**: Bets against the majority when odds are favorable
  - **With Strategy**: Bets with the majority when conditions are optimal
- **Automatic Claiming**: Automatically claims winnings and handles refunds
- **Dynamic Timing**: Adjusts betting timing based on network conditions
- **Real-time Monitoring**: Live console output with colored status updates
- **Error Handling**: Robust error handling with automatic retry mechanisms

## 📋 Prerequisites

- Node.js (v14 or higher)
- npm or yarn package manager
- BSC (Binance Smart Chain) wallet with BNB for betting
- Private key for your wallet

## 🛠️ Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/mooncitydev/crypto-prediction-bot.git
   cd PredictionBot-main
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Set up environment variables**
   Create a `.env` file in the root directory:
   ```env
   PRIVATE_KEY=your_wallet_private_key_here
   BET_AMOUNT=0.1
   ```

## ⚙️ Configuration

### Environment Variables

| Variable | Description | Default | Required |
|----------|-------------|---------|----------|
| `PRIVATE_KEY` | Your wallet's private key | - | ✅ Yes |
| `BET_AMOUNT` | Amount of BNB to bet per round | 0.1 | ❌ No |

### Contract Addresses

- **PancakeSwap Prediction V2**: `0x18B2A687610328590Bc8F2e5fEdDe3b582A49cdA`
- **CandleGenie Prediction V3**: `0x995294CdBfBf7784060BD3Bec05CE38a5F94A0C5`

## 🎯 Usage

### PancakeSwap Predictions

**Against Strategy (Default)**
```bash
npm run start
```

**With Strategy**
```bash
npm run start -- --with
```

### CandleGenie Predictions

**Against Strategy (Default)**
```bash
npm run cg
```

**With Strategy**
```bash
npm run cg -- --with
```

## 🧠 How It Works

### Betting Strategies

1. **Against Strategy**: 
   - Analyzes bull vs bear betting amounts
   - Places bets against the majority when the ratio is favorable (< 5:1)
   - Exploits market inefficiencies and herd behavior

2. **With Strategy**:
   - Bets with the majority when conditions suggest momentum
   - Uses similar ratio analysis but follows the crowd

### Timing Mechanism

- Waits ~281.5 seconds after round start before placing bets
- Dynamically adjusts timing based on network congestion
- Reduces wait time by 6 seconds (2 blocks) if transactions fail

### Automatic Features

- **Claiming**: Automatically claims winnings from previous rounds
- **Refunds**: Handles refunds for invalid rounds
- **Dues**: Sends 2% of winnings to specified address (`0x74b8B9b7aa13D26056F4eceBDF06C917d15974C7`)

## 📊 Project Structure

```
src/
├── index.ts              # PancakeSwap bot main file
├── candle-genie.ts       # CandleGenie bot main file
├── lib.ts                # Shared utilities and strategies
└── types/
    └── typechain/        # Generated contract type definitions
        ├── CandleGeniePredictionV3.d.ts
        ├── PancakePredictionV2.d.ts
        └── factories/
```

## 🔧 Development

### Running Tests
```bash
npm test
```

### TypeScript Compilation
The project uses TypeScript with the following configuration:
- Target: ES5
- Module: CommonJS
- Strict mode enabled

## ⚠️ Important Notes

### Risk Disclaimer
- **This bot involves financial risk**. Only use funds you can afford to lose
- Past performance does not guarantee future results
- Cryptocurrency trading is highly volatile and unpredictable
- The bot's strategies are based on historical patterns and may not work in all market conditions

### Security Considerations
- Never share your private key
- Use a dedicated wallet for bot trading
- Monitor your bot's performance regularly
- Keep your private key secure and never commit it to version control

### Network Considerations
- The bot uses BSC mainnet by default
- Ensure you have sufficient BNB for gas fees
- Network congestion may affect transaction timing

## 📈 Performance Tips

1. **Start Small**: Begin with small bet amounts to test the bot
2. **Monitor Closely**: Watch the bot's performance for the first few rounds
3. **Network Conditions**: Consider network congestion when setting bet amounts
4. **Strategy Selection**: Test both "against" and "with" strategies to see what works best

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Egor Gavrilov** - Initial work

## 🆘 Support

If you encounter any issues or have questions:

1. Check the console output for error messages
2. Verify your private key and BNB balance
3. Ensure your network connection is stable
4. Review the contract addresses are correct

**Need Help?** Contact the developer:
- Telegram: [@moooncity](https://t.me/moooncity)

---

**Remember**: Trading cryptocurrencies involves substantial risk of loss and is not suitable for all investors. The high degree of leverage can work against you as well as for you. Before deciding to trade cryptocurrency, you should carefully consider your investment objectives, level of experience, and risk appetite.
