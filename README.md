# Investment Calculator

A standalone, dependency-free investment calculator that helps you visualize long-term savings growth with compound interest. Built as a single HTML file with no external dependencies.

![Investment Calculator](https://img.shields.io/badge/version-1.0.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## Features

- 📊 **Dual Chart Visualization**
  - Total Capital growth over 30 years
  - Monthly passive income projection

- 📋 **Detailed Data Table**
  - Year-by-year breakdown
  - Starting and ending capital
  - Annual deposits and interest earned
  - Cumulative investment tracking

- 💰 **Flexible Inputs**
  - Initial capital (starting investment)
  - Annual return rate (%)
  - Monthly savings amount

- 🎯 **Real-time Updates**
  - Charts and table update instantly as you adjust inputs

- ✅ **Comprehensive Unit Tests**
  - 12 automated tests covering all calculation logic
  - Verifies accuracy of compound interest formulas

## Demo

Open `investment-calculator.html` directly in any modern web browser.

### Example Calculation

With default values:
- **Initial Capital:** €100
- **Annual Return Rate:** 10%
- **Monthly Savings:** €10

**Results after 3 years:**

| Year | Starting Capital | Annual Deposit | Interest Earned | Ending Capital | Total Invested |
|------|------------------|----------------|-----------------|----------------|----------------|
| 1    | €100            | €120           | €10             | €230           | €220           |
| 2    | €230            | €120           | €23             | €373           | €340           |
| 3    | €373            | €120           | €37             | €530           | €460           |

## How It Works

### Calculation Formula

The calculator uses a year-by-year compound interest approach:

```
Interest Earned = Starting Capital × Annual Rate
Annual Deposit = Monthly Savings × 12
Ending Capital = Starting Capital + Annual Deposit + Interest Earned
Monthly Income = Ending Capital × Annual Rate / 12
```

### Key Concepts

- **Starting Capital**: The amount at the beginning of each year (previous year's ending capital)
- **Annual Deposit**: Your total yearly contributions (monthly savings × 12)
- **Interest Earned**: Returns generated on your starting capital for that year
- **Ending Capital**: Total value at year-end (becomes next year's starting capital)
- **Total Invested**: Cumulative sum of all your contributions (initial + deposits)
- **Monthly Income**: Potential passive income if you stopped contributing

## Installation

No installation required! Just download and open:

```bash
# Clone the repository
git clone https://github.com/yourusername/investment-calculator.git

# Open in your browser
open investment-calculator.html
```

Or serve with a local server:

```bash
# Using Python
python3 -m http.server 8000

# Then navigate to
# http://localhost:8000/investment-calculator.html
```

## Usage

1. **Adjust Input Values**
   - Set your initial capital (if any)
   - Choose your expected annual return rate
   - Enter your monthly savings amount

2. **View Results**
   - Charts update automatically
   - Scroll through the 30-year projection table
   - See monthly passive income potential

3. **Experiment**
   - Try different scenarios
   - Compare return rates
   - See the impact of starting capital

## Testing

The calculator includes comprehensive unit tests to ensure accuracy.

### Run Tests

Open `investment-calculator.test.html` in your browser to run all tests automatically.

### Test Coverage

- ✅ Year-by-year calculation accuracy
- ✅ Interest earned formula
- ✅ Total invested accumulation
- ✅ Monthly income calculation
- ✅ Initial capital handling
- ✅ Data structure validation
- ✅ Edge cases (zero savings, different rates)

**Example Test Results:**
```
✓ Year 1: Starting=100, Deposit=120, Interest=10, Ending=230, Invested=220
✓ Year 2: Starting=230, Deposit=120, Interest=23, Ending=373, Invested=340
✓ Year 3: Starting=373, Deposit=120, Interest=37, Ending=530, Invested=460
✓ Ending capital equals starting + deposit + interest
✓ Interest earned equals starting capital × annual rate
```

## Project Structure

```
investment-calculator/
├── investment-calculator.html      # Main application (standalone)
├── investment-calculator.test.html # Unit tests (standalone)
├── CLAUDE.md                       # Development guidelines
└── README.md                       # This file
```

### Architecture

- **Single-file application**: No build process or dependencies
- **Vanilla JavaScript**: ES6+ with class-based architecture
- **Custom canvas charts**: No charting libraries required
- **Responsive design**: Mobile-first CSS Grid layout
- **Object-oriented**: Clean `InvestmentCalculator` class structure

## Key Implementation Details

### Calculation Method

Unlike simple compound interest formulas, this calculator uses **annual compounding with regular deposits**:

- Each year's interest is calculated on the starting capital only
- Monthly deposits accumulate throughout the year
- The ending capital becomes the next year's starting capital
- This provides a realistic view of how investments grow over time

### Why This Approach?

This method accurately reflects real-world investment scenarios where:
- You make regular monthly contributions
- Interest compounds annually on your capital
- Returns are calculated on the balance at the start of each period

## Browser Compatibility

Works on all modern browsers:
- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+

## Customization

### Modify Defaults

Edit the HTML file to change default values:

```html
<input type="number" id="initialCapital" value="100" min="0" step="100">
<input type="number" id="annualReturn" value="10" min="0" max="100" step="0.1">
<input type="number" id="monthlySavings" value="10" min="0" step="10">
```

### Change Time Horizon

Modify the calculation period (default: 30 years):

```javascript
const maxYears = 30; // Change this value
```

### Styling

All CSS is embedded in the HTML file. Look for the `<style>` section to customize:
- Colors
- Chart dimensions
- Table styling
- Layout breakpoints

## Use Cases

- 📈 **Retirement Planning**: Project your nest egg growth
- 💡 **Goal Setting**: See how long to reach financial targets
- 🎓 **Financial Education**: Understand compound interest visually
- 🔄 **Scenario Comparison**: Test different savings strategies
- 📊 **Investment Analysis**: Evaluate expected returns

## Limitations

- Assumes constant annual return rate (markets vary)
- Does not account for inflation
- No tax considerations
- Simple annual compounding (actual investments may compound differently)
- Fixed monthly contribution amounts

## Contributing

Contributions are welcome! This is a simple educational tool, but improvements are always appreciated.

### Ideas for Enhancement

- [ ] Add inflation adjustment
- [ ] Support different compounding frequencies (monthly, quarterly)
- [ ] Export data to CSV
- [ ] Multiple investment scenarios side-by-side
- [ ] Tax-adjusted calculations
- [ ] Variable contribution amounts over time

## License

MIT License - Feel free to use, modify, and distribute.

## Disclaimer

This calculator is for educational and planning purposes only. It does not constitute financial advice. Past performance does not guarantee future results. Always consult with a qualified financial advisor before making investment decisions.

## Author

Created as a simple, dependency-free tool for understanding long-term investment growth.

## Acknowledgments

Built with:
- Pure JavaScript (ES6+)
- HTML5 Canvas API
- CSS Grid Layout
- No external dependencies 🎉

---

**Happy Investing! 📈💰**
