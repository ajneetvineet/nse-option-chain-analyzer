# NSE Option Chain Analyzer | TMPV Edition

Real-time interactive option chain analyzer for NSE F&O derivatives with AI-powered trading signals.

## 📊 Features

- **Live Option Chains**: View complete call and put option chains with real-time LTP, OI, and volume
- **Smart Trading Signals**: Automatic BUY/SELL recommendations based on OI analysis
- **Market Sentiment**: PCR (Put-Call Ratio) analysis with bullish/bearish indicators
- **Strategy Guide**: Pre-built trading strategies for different market conditions
- **Interactive Charts**: OI distribution visualization with Chart.js
- **Mobile Optimized**: Fully responsive design for trading on the go
- **Shareable Links**: Generate and share specific stock/expiry combinations

## 🎯 Supported Stocks (TMPV Edition)

| Ticker | Company | Sector | Data Source |
|--------|---------|--------|-------------|
| BHARTIARTL | Bharti Airtel | Telecom | NSE EOD 07-MAY-2026 |
| JIOFIN | Jio Finance | Finance | NSE EOD 07-MAY-2026 |
| SBIN | State Bank of India | Banking | NSE EOD 07-MAY-2026 |
| TATASTEEL | Tata Steel (TMPV) | Metals | NSE EOD 07-MAY-2026 |

## 🚀 Quick Start

### Online Access
Open `option_chain_nse.html` directly in any modern web browser:
- Chrome, Firefox, Safari, Edge (all versions)
- Mobile browsers (iOS Safari, Chrome Mobile)
- No installation or dependencies required

### Local Setup
1. Clone or download this repository
2. Open `option_chain_nse.html` in your browser
3. Select a stock and expiry date
4. Analyze the option chain and signals

### Mobile Access
**Generate a shareable link for mobile access:**
- Click the "📱 Mobile Link" box in the header
- Copy the link and send to your device
- Works on any mobile browser - no app installation needed

## 📈 How to Use

### Step 1: Select a Stock
Click on any of the four stock cards (BHARTIARTL, JIOFIN, SBIN, TATASTEEL) to load its option chain.

### Step 2: Choose an Expiry
Select from available expiries:
- **26-MAY-2026** (Weekly)
- **30-JUN-2026** (Monthly)
- **28-JUL-2026** (Monthly)

### Step 3: Analyze the Option Chain
**Column Meanings:**
- **Signal (CE/PE)**: Trading recommendation
- **LTP**: Last Traded Price
- **OI**: Open Interest (position count)
- **Strike**: Exercise price (highlighted in gold for ATM)
- **Volume**: Number of contracts traded

### Step 4: Check Market Analysis
The sidebar shows:
- **PCR (OI)**: Put-Call Ratio for sentiment analysis
- **ATM Straddle**: Cost of buying ATM Call + Put
- **Sentiment Gauge**: Visual indicator of market bias
- **OI Chart**: Distribution of call vs put positions
- **Strategy Recommendations**: Pre-built strategies matching current sentiment

## 🔍 Trading Signals Explained

### Signal Levels
| Signal | Meaning | Action |
|--------|---------|--------|
| **BUY CE** | Strong call interest | Buy call options |
| **SELL CE** | High call OI concentration | Sell calls (defensive) |
| **BUY PE** | Strong put interest | Buy put options |
| **SELL PE** | High put OI concentration | Sell puts (defensive) |

### Signal Generation
Signals are based on:
1. **Maximum OI Strike**: Identifies key support/resistance levels
2. **ATM Region**: Identifies most volatile strikes
3. **PCR Analysis**: Determines overall market sentiment

## 📊 Market Analysis Indicators

### PCR (Put-Call Ratio)
- **PCR > 1.3**: Bullish market (more puts than calls)
- **PCR < 0.9**: Bearish market (more calls than puts)
- **0.9-1.3**: Neutral market

### ATM Straddle
- Shows the cost of buying both ATM call and put
- Higher straddle = higher expected volatility
- Lower straddle = lower expected volatility

### Sentiment Gauge
Visual bar showing:
- **Red (Left)**: Bearish
- **Yellow (Center)**: Neutral
- **Green (Right)**: Bullish

## 💡 Trading Strategies

### Bullish Scenarios (PCR > 1.3)
1. **Buy ATM Call**: Profit from upside with defined risk
2. **Bull Call Spread**: Buy ATM call + Sell OTM call
3. **Sell OTM Put**: Collect premium while awaiting upside

### Bearish Scenarios (PCR < 0.9)
1. **Buy ATM Put**: Profit from downside with defined risk
2. **Bear Put Spread**: Buy OTM put + Sell ATM put
3. **Sell OTM Call**: Collect premium while awaiting downside

### Neutral Scenarios (0.9 < PCR < 1.3)
1. **Short Straddle**: Sell ATM call + put (profit from lack of movement)
2. **Iron Condor**: Sell OTM call + put, Buy further OTM options
3. **Long Straddle**: Buy ATM call + put (profit from big moves)

## ⚙️ Technical Details

### Technologies Used
- **Frontend**: Vanilla JavaScript (no frameworks)
- **Charts**: Chart.js 3.9.1
- **Data Format**: Embedded JSON (no external API calls)
- **Responsive Design**: CSS Grid & Flexbox
- **Styling**: CSS Variables for theming

### File Structure
```
option_chain_nse.html         - Main interactive analyzer (~99 KB)
README.md                      - This documentation
CONTRIBUTING.md                - Contribution guidelines
LICENSE                        - MIT License
.gitignore                    - Git ignore file
```

### Data Format
The HTML file contains embedded JSON data for all stocks:
```javascript
{
  "BHARTIARTL": {
    "spot": 1826.6,
    "expiries": {
      "26-MAY-2026": [
        {
          "strike": 1820,
          "option_type": "CE",
          "ltp": 44.4,
          "oi": 15000,
          "volume": 500,
          "spot": 1826.6
        }
      ]
    }
  }
}
```

## 📱 Mobile Features

### Responsive Breakpoints
- **Desktop**: Full multi-column layout
- **Tablet**: 1200px and below - Single column with sidebar below
- **Mobile**: 768px and below - Optimized card layout

### Touch-Friendly
- Large tap targets (minimum 44px)
- Horizontal scroll for option chain table
- Sticky header for easy navigation

## 🔗 Shareable Links

Generate custom links for specific stocks/expiries:
```
option_chain_nse.html?stock=BHARTIARTL&expiry=26-MAY-2026
option_chain_nse.html?stock=SBIN&expiry=30-JUN-2026
```

These links preserve your selection when shared.

## 📊 Data Source

**NSE EOD File**: `op070526.csv` (07-May-2026)
- **Records**: 39,584 option contracts
- **Expiries**: 26-MAY-2026, 30-JUN-2026, 28-JUL-2026
- **Last Updated**: 07-MAY-2026 (EOD)
- **Format**: CSV with 14 columns

## ⚠️ Disclaimer

**Educational Purpose Only**

This tool is provided for educational and informational purposes only. It is **NOT** financial advice. 

- All data is historical (EOD 07-MAY-2026)
- Past performance does not guarantee future results
- Options trading involves significant risk of loss
- **Always consult a qualified financial advisor before making investment decisions**
- The authors assume no responsibility for losses incurred from using this tool

**Risk Warning**: Options are leveraged instruments. You can lose more than your initial investment.

## 📈 Performance & Limitations

### Supported Browsers
- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+
- ✅ Mobile browsers (iOS Safari, Chrome Mobile)

### Data Limitations
- Data is EOD (End of Day) as of 07-MAY-2026
- Real-time data requires API integration (not included)
- Historical data for backtesting not included
- Volume data represents EOD traded quantity

### Known Limitations
- No real-time updates (manual refresh required)
- No user authentication or data persistence
- No order placement capability
- Single data file (can't load multiple dates)

## 🚀 Future Enhancements

Potential additions for future versions:
- [ ] Real-time data integration (WebSocket)
- [ ] Multiple date ranges
- [ ] Greek calculations (Delta, Gamma, Theta, Vega)
- [ ] Backtesting engine
- [ ] User watchlists
- [ ] Order management
- [ ] Push notifications
- [ ] Dark/Light theme toggle

## 💻 Development

### Building from Source
The HTML file is self-contained and requires no build process:
1. Edit `option_chain_nse.html` directly
2. Refresh browser to see changes
3. No compilation or bundling needed

### Contributing
See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## 📞 Support

**Questions or Issues?**
1. Check this README for common questions
2. Review the disclaimer and limitations
3. Verify you're using a supported browser
4. Ensure JavaScript is enabled

**Data Issues?**
- Data source: NSE EOD file dated 07-MAY-2026
- File format: CSV
- Stocks included: BHARTIARTL, JIOFIN, SBIN, TATASTEEL only
- Not all NSE stocks are included - only those with sufficient option liquidity

## 📄 License

MIT License - See LICENSE file for details

---

**Version**: 1.0.0 (TMPV Edition)  
**Last Updated**: 07-MAY-2026  
**Data Date**: 07-MAY-2026 EOD  
**Created**: 2026
