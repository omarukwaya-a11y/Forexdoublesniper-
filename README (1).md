# ForexDoubleSniper – Gold signal

Live XAU/USD price, trend, news sentiment and a BUY / SELL / WAIT decision.

## Deploy on Vercel
1. Get free API keys:
   - Twelve Data: https://twelvedata.com  (prices, XAU/USD)
   - Finnhub: https://finnhub.io  (market news)
2. Upload this folder to a GitHub repo, then Vercel > Add New > Project > import it.
   (Or unzip and run `npx vercel` in the folder.)
3. In Vercel > Project > Settings > Environment Variables add either
   - OANDA_TOKEN and OANDA_ACCOUNT_ID (set OANDA_HOST to https://api-fxpractice.oanda.com for a practice account), or
   - TWELVEDATA_KEY
   - FINNHUB_KEY   (optional; without it the decision uses trend only)
4. Deploy. Framework preset: "Other". No build command needed.

## How the decision works
- Trend: 10 vs 30 candle average on 15-minute data
- Today's move: % change vs previous close
- News tone: keyword scoring of recent forex/general headlines
- Stop-loss 1.5 x ATR, take-profit 3 x ATR

Not financial advice. No signal is guaranteed. Backtest before using real money.
