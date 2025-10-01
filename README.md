# Bitcoin Technical Analysis Automation

Automated Bitcoin technical analysis and reporting system. This n8n workflow fetches live data from Binance, performs comprehensive technical analysis, and delivers AI-powered reports via email and Google Sheets.

## 🎯 Features

- **Automatic Data Collection**: Fetches data from Binance public APIs every 4 hours
- **Comprehensive Technical Analysis**: SMA, EMA, RSI, MACD, Bollinger Bands, Stochastic, VWAP, ATR
- **AI-Powered Insights**: Detailed market analysis using DeepSeek R1 model
- **Visual Reporting**: Professional HTML-formatted email reports
- **Data Archiving**: Automatic logging to Google Sheets

## 📋 Requirements

- n8n installation (self-hosted or cloud)
- Gmail account (OAuth2 integration)
- Google Sheets API access
- OpenRouter API key (for DeepSeek R1 model)

**Note**: No Binance API key required - all data is fetched from public endpoints.

## 🚀 Setup

1. **Import n8n Workflow**
   ```bash
   n8n import:workflow --input=BTC-Price-Report.json
   ```

2. **Configure Credentials**
   - Gmail OAuth2 (for email sending)
   - Google Sheets OAuth2 (for data logging)
   - OpenRouter Bearer Token (for AI analysis)

3. **Workflow Settings**
   - `Schedule Trigger`: Set execution frequency (default: 4 hours)
   - `Send a message`: Update recipient email address
   - `BTC Price Data`: Configure Google Sheets document ID

4. **Activate Workflow**

## 🔧 API Endpoints Used

```
GET https://api.binance.com/api/v3/ticker/24hr?symbol=BTCUSDT
GET https://api.binance.com/api/v3/klines?symbol=BTCUSDT&interval=4h&limit=180
POST https://openrouter.ai/api/v1/chat/completions
```

## 📊 Analysis Scope

**Technical Indicators:**
- Moving Averages: SMA(20,50,200), EMA(12,26), VWAP
- Momentum: RSI(14), Stochastic K, MACD
- Volatility: Bollinger Bands, ATR(14)
- Support/Resistance: Pivot Points, current levels

**AI Analysis:**
- Market condition assessment
- Short/medium-term outlook
- Buy-sell strategy recommendations
- Stop-loss and take-profit levels
- Risk management advice

## 📧 Report Format

Email reports include:
- Market summary and current price
- Detailed technical indicator tables
- AI-powered analysis and strategy recommendations
- Critical support/resistance levels
- Visual trend indicators

## 📝 License

MIT License

## ⚠️ Disclaimer

This system is for informational purposes only and does not constitute investment advice. Cryptocurrency investments carry high risk. Always conduct your own research and apply proper risk management principles.
