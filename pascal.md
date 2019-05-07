# Pascal project - Notes

## Currency market
- One can buy EUR/DOLLAR
    - Bid/offer

## Actors:
- Buyers
- Sellers
- Market-makers (usually trading at second)
- Speculators (we)
- Investors (also we)

Digital currency - open technology

Currency market - natural next step

Stock market - the next step after

## Types of markets:
- Equities
- Fixed income
- Currencies
- Commodities
- Alternative assets(digital currencies, real estate, etc.)

## Equities:
- BT issues equities 
- By buying these equities, you become a shareholder
    - As a shareholder you are entitled for profit of BT (you are entitled for a share of their profits)
    - You have the right to share
- If it defaults (goes bankrupt) you lose everything

## Fixed Income:
- BT needs to invest (buy cable)
- They issue debt, say £100m
- You buy that debt (Provide the loan, don't own the company)
- Issues a coupon (5% /year+ initial capital after 10 years)
- Every year they give 5%
- At the end of the 10 years the company has to give the initial capital back

## Commodities (oil, gas, platinum, cotton, etc.):
- BT buying platinum for their cable
- Some companies have relationships with platinum providers
    - They stock platinum
    - they sell it to BT through an exchange

## Securities:
- Equities
- Debt

## Equity (stockholder's equity / shareholder's equity / book value)
- Assets - Liabilities = Equity

## Derivative:
- A financial security with a value that is reliant upon, or derived from, an underlying asset or group of assets
- Swaps (e.g. FT Interest to variable interest)
- Futures
- Forwards (over-the-counter)
- Options (like futures, but the buyer is not obliged to "exercise" the contract while the seller is) - Strike price
    - Put options (hedging against falling prices)
    - Call option

---

# Bid-ask spread
- The difference between the **ASK PRICE** and the **BID PRICE**
- Or, the highest price a buyer is willing to spend, and the smallest price a seller is willing to sell for

## Bid-ask spread relation to liquidity
- Certain markets are more liquid than others
- Small spread (.001% bid-ask spread for cash) means **high liquidity** (in cash markets, offer price is close to bids)
- Large bid-ask spread means **low liquidity** (e.g. real estate markets, where the offer prices are much larger than bids)
- Another example: art and collectibles market -> Relatively liquid

## Liquidity
- The degree to which an **asset** or **security** can be quicky bought or sold in the market without affecting the asset's price

## Market liquidity
- e.g. A city's real estate market or a country's stock market
- The extent to which items can be bought and sold on these markets at **stable prices**

## Accounting liquidity
- for and entity (person/company) it is a measure of the **ability to pay off debts as they come due**
- comparing liquid assets to current liabilities or financial obligations that come due within a year

### Current ratio = Current assets ÷ Current liabilities
- Current assets are those that can reasonably be converted to cash in one year
- Current liabilities are debt or obligations that are due within a year

---

## Hedge funds:
- Definition of "hedge"
    - A fence or boundary formed by closely growing bushes
    - Protecting oneself from financial loss
1) Open to accredited investors
2) They offer wider investment latitude than other funds
3) Often employ leverage (devt to increase risk capital returns)
4) Fee structure (expense ratio and performance fee)

Leverage:
- **investment strategy** of using **borrowed money**
- Using borrowed money to fund the firm's asset base and generate returns on risk capital

Liability:
- An obligation or something you owe to somebody else

### Balance sheet
- A financial statement
- Reports a company's assets, liabilities, shareholder's equity at a specific pont in time
- Provides basis for computing rates of return and evaluating the **capital structure**
`ASSETS = LIABILITY + SHAREHOLDER EQUITY`

### Market cap (Market capitalisation)
- Shares outstanding * Proce per share
- Authorised, issued and purchased financial assets or shares of a corporation held by investors

---
## Net worth:
- The amount by which assets exceed liabilities
- Deduce debts from assets

### Debt
#### Good debt:
- Helps increase the net worth

#### Bad debt:
- Borrow money to purchase depreciating assets

--- 

## Volume of trade
- Total quantity of shares or contracts traded for a specific security
- Measured on any type of security traded during a trading day

- Higher volumes for a specified security means higher liquidity

- Price change on low volume - insignificant
- Price change on high volume - strong signal that something has changed in the stock has changed fundamentally

## Exhaustion moves and volumes:
- In a rising or falling market we can see exhaustion moves
- Generally, sharp moves in price combined with a sharp increase in volume, which signal the potential end of a trend

## Bullish signs:
- e.g. Volume increases on a price fall and reach a price A
- Then the prices increase to B
- Followed by a move back lower to a price C
- If C is higher than A, and volume is diminished on the second decline, then it is usually interpreted as a bullish sign

## Volatility:
- Measure of dispersion of returns for a given security or index

---

## VIDYA (1992) - Variable Index Dynamic Average
## VMA - Variable Moving Average
`VMA = (⍺ * close) + (1 - (⍺ * VI) * VMA[1])`

`⍺ = 2 ÷ (N + 1)`
`VI` - Volatility Index
`N` - smoothing period (higher N will result in slower VMA. Interesting to experiment with)
`VMA[1]` = Previous VMA value

`VI = |(Su - Sd) ÷ (Su + Sd)|`
`Su` = Sum of difference between current close and previous closes on days with a positive price movement within the selected period (typically 9 days)
`Sd` = Sum of difference between \[...\] with a negative price movement \[...\]

## Moving average / Rolling average / Running average
- Help smoothen out the fluctuation in the series
- Larger subsets (choice of **n**) will result in smoother curves - **Slow Moving Averages**
- Smaller subsets have more fluctuation because the subsets' values have more weight - **Fast Moving Averages**

The table below shows a Moving Average with `n = 5`

| Series |  7 | 12 |  2 | 14 | 15 |  6 | 11 | 20 |  7 | Avg |
| ------ | -- | -- | -- | -- | -- | -- | -- | -- | -- | --- |
| 1st MA | xx | xx | xx | xx | xx |    |    |    |    |= 10 |
| 2nd MA |    | xx | xx | xx | xx | xx |    |    |    |=11.8|
| 3rd MA |    |    | xx | xx | xx | xx | xx |    |    |=11.6|


### Simple Moving Average
- Arithmetic moving average

### Exponential Moving Average
- More recent data has (exponentially) greater weight
- Reacts faster to rapid changes than SMA
- User can change weighting

### Weighted Moving Average (WMA / LWMA)
- Linearly weighted MA's give linearly increasing weights to data as opposed to exponentially higher weights of EMA's

### Triangular Moving Average
- Double smoothed curve `(SMA1 + SMA2 + ... + SMAn) / n`
- Slowest to respond to changes

### Variable Moving Average
- Exponentially weighted moving average
- Use the Volatility Index to adjust the smoothing period when the markets change
