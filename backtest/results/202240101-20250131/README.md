# Backtest

## Results

The two sets of results share common rules except for the stop order.

These are raw trades and do not include commission, slippage, market filters, progressive exposure rules, etc.

The intent is traders can use these results as a starting point for further research.

## Rules

### Scan Filter

Momentum leader (30, 90, 180 day) from previous Friday scan before trade entry date.

Scan rules are:

- Close >= 5
- Close >= 50 SMA
- Average Daily Volume >= 250,000
- Average Daily Dollar Volume >= 6,000,000
- ADR (Average Daily Range) >= 4%
- Percent return >= 30% for N period
- In top 100 Percentage Gainers

The three momentum lists (30, 90, 180 day) are consolidated into a single list of 100 percentage gainers where new momentum is ranked higher.

### Strategy Rules

#### Entry

- Setup (variety of break out setups) visually idenified via chart pattern.
- Trigger price identified, typically above a recent pivot point or trendline.
- Entry is when 1 minute close closes above 2 minute opening range high and trigger price.

#### Exit

#### Partial Profit

- Half of position is sold at (entry price + (ADR (Average Daily Range) x 3)).

#### Signal

- Close position at next open when position has been opened for at least 3 days and close < 10 SMA.

#### Stop

##### Low of Day

- Stop is Low of Day. Results are are at [stop-lod](stop-lod).

##### ADR Factor

- Stop is (entry price - (ADR (Average Daily Range) x 1)). Results are are at [stop-adr-factor](stop-adr-factor).
