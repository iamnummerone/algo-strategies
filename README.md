# Market Structure - BOS/CHoCH Indicator

A professional Pine Script v6 indicator for detecting market structure, swing points, Break of Structure (BOS), and Change of Character (CHoCH) signals on TradingView.

## Features

- ✅ **Non-repainting**: Uses only confirmed closed bars (lookahead_off)
- 📊 **Higher Timeframe Analysis**: Detect structure on any HTF (1M, 1W, 1D, 4H, etc.) and display on current chart
- 🎯 **Swing Detection**: Robust fractal-based swing high/low identification
- 🔄 **BOS & CHoCH Labels**: Automatically identifies and labels Break of Structure and Change of Character
- 📏 **Swing Ranges**: Visual horizontal ranges showing current swing boundaries
- 🎨 **Clean Visuals**: Grey swing dots, green/red BOS/CHoCH labels, neutral swing range lines

## Installation

1. Open TradingView
2. Click on "Pine Editor" at the bottom of the screen
3. Copy the entire contents of `market_structure_indicator.pine`
4. Paste into the Pine Editor
5. Click "Add to Chart"

## How It Works

### Swing Detection
- Uses a centered fractal approach to identify swing highs and lows
- Swing high: Price at center is higher than N bars on both sides
- Swing low: Price at center is lower than N bars on both sides
- Enforces minimum distance between swings to avoid noise

### BOS & CHoCH Logic
- **CHoCH (Change of Character)**: Occurs when price breaks structure in the opposite direction of current trend
  - Bearish → Bullish: Price breaks above last swing high
  - Bullish → Bearish: Price breaks below last swing low
- **BOS (Break of Structure)**: Occurs when price breaks structure in the same direction as current trend
  - Bullish: Price breaks above last swing high while in uptrend
  - Bearish: Price breaks below last swing low while in downtrend

### Swing Ranges
- Displays horizontal lines showing the current major swing boundaries
- Upper line: Last significant swing high
- Lower line: Last significant swing low
- Label shows the HTF timeframe (e.g., "Swing 1D", "Swing 4H")

## Settings

### Structure Settings
- **Higher Timeframe**: Timeframe for structure detection (default: "D")
- **Swing Length**: Number of bars on each side for fractal detection (default: 3, range: 2-10)
- **Minimum Swing Distance**: Minimum bars between consecutive swings (default: 2)
- **Break Buffer %**: Buffer to avoid false breaks (default: 0.0005 = 0.05%)

### Display Options
- **Show BOS/CHoCH Labels**: Toggle BOS and CHoCH labels (default: true)
- **Show Swing Range Lines**: Toggle horizontal swing range lines (default: true)
- **Show Swing Dots**: Toggle grey circles on swing points (default: true)
- **Max History Swings**: Limit stored swings for performance (default: 200)

### Colors
- **Bullish Color**: Color for bullish BOS/CHoCH (default: green)
- **Bearish Color**: Color for bearish BOS/CHoCH (default: red)
- **Swing Dot Color**: Color for swing point circles (default: grey)
- **Swing Range Color**: Color for swing range lines (default: grey)

## Usage Tips

1. **Choose Your HTF Wisely**: 
   - For day trading: Use 4H or 1D
   - For swing trading: Use 1D or 1W
   - For position trading: Use 1W or 1M

2. **Adjust Swing Length**:
   - Smaller values (2-3): More swing points, more sensitive
   - Larger values (5-10): Fewer swing points, major structure only

3. **Combine with Other Analysis**:
   - Use with support/resistance zones
   - Confirm with volume analysis
   - Look for confluence with other indicators

4. **Performance Optimization**:
   - Reduce `Max History Swings` if chart loads slowly
   - Disable features you don't need (dots, labels, or lines)

## Technical Details

- **Pine Script Version**: v6
- **Overlay**: true
- **Max Lines**: 500
- **Max Labels**: 500
- **Max Boxes**: 500
- **Repainting**: None - all signals confirmed on bar close

## Important Notes

- **No Repainting**: All detections happen only after bar close
- **HTF Alignment**: Structure is detected on the specified HTF, not current timeframe
- **Buffer System**: Small buffer prevents false signals from minor price fluctuations
- **Memory Management**: Arrays are limited to prevent TradingView execution limits

## Example Configurations

### Scalping/Intraday (15m chart)
- HTF: 1H or 4H
- Swing Length: 3
- Min Swing Distance: 2

### Day Trading (1H chart)
- HTF: 4H or 1D
- Swing Length: 3-4
- Min Swing Distance: 3

### Swing Trading (1D chart)
- HTF: 1W
- Swing Length: 4-5
- Min Swing Distance: 3-5

### Position Trading (1W chart)
- HTF: 1M
- Swing Length: 5-7
- Min Swing Distance: 5

## Credits

Developed from scratch as a custom implementation inspired by market structure concepts. This is an original implementation and not a copy of any existing script.

## License

Free to use for personal trading. Please credit if sharing publicly.
