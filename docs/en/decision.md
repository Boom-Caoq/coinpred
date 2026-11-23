# When analysis is more usable, and when you should not place an order

**Languages:** [English](decision.md) · [简体中文](../zh/decision.md)

This page is about when the evidence is more consistent — and when you should stand aside — if you are doing the analysis by hand. It is **not** permission to “trust the model, then place an order.”

Coinpred’s outputs — fusion scores, JEV direction and confidence, Kronos future candles, and the TradingView signal review — are for research only. They are not investment advice and not an order ticket. Event contracts and other derivatives can take the entire stake if the direction is wrong. Confirm that this product is legal where you are. The service is not available to users in mainland China.

Treat every output as a structured second opinion: read the chart, the rules and the size yourself first, then use the model to check for evidence you missed. No output can do those steps for you.

## First, know which tool you are looking at

The four systems have different inputs and different published track records. Do not mix them:

| What you are looking at | What it can tell you | What it cannot tell you |
| --- | --- | --- |
| 19-algorithm fusion | The weighted long/short call for this run, a calibrated P(up), per-algorithm contributions and liquidation locations | The site does not yet publish a contract-settled win-rate table for fusion calls themselves. “Backtest hit rate” is an in-tool historical fit |
| JEV | A five-level direction, how concentrated the probability mass is, and program-assembled evidence | Confidence is not a win rate and not an event-contract payout probability. No out-of-sample JEV record has been published |
| Kronos | What the next candles might look like, and close error versus later realized closes in the daily archive | Close error is not a trading return and not an order win rate |
| TradingView signal review | The public, row-by-row automated signal win rate currently on the site | Those records are not JEV, not Kronos, and they do not endorse every script in the strategy store |

The checklist below only helps after you know which system you are reading, and whether that system has a published win rate.

## When the evidence is usually more consistent

The more of these conditions you can actually tick, the more suitable the analysis is as a *cross-check* — not as a licence to trade. Missing any one of them does not mean “you may place the order.”

1. **You already understand the venue’s rules.** Expiry, the settlement-price source, the payout ratio and the tie rule have been checked, and you know the candle interval is not the contract expiry. If the rules are still unread, no model is ready to use.
2. **The size is one you can afford to lose.** A wrong event-contract call usually costs the entire stake. Set that limit before you look at the model, not after.
3. **The probability mass is concentrated, not merely a large-looking number.** For JEV, look at whether the five direction probabilities sit on one side. If the distribution is spread out, a high confidence figure cannot be used on its own. Confidence measures how certain this classification is, not how often that kind of trade has paid.
4. **Neighbouring timeframes are not obviously in conflict.** Shorter intervals are noisier. If 15m and 1h — or the timeframes near your actual expiry — disagree, the evidence is not consistent.
5. **The leading evidence is not fighting the location information.** In the fusion console, that means you have looked at the top contributors, the contrary algorithms and the liquidation map, and the suggested stop is not sitting in a liquidation cluster. Reading only the final “long” or “short” is not enough.
6. **You can re-check the evidence on the tape.** JEV’s “evidence” is assembled by the application, not a chain of thought from inside the model. For Kronos, first confirm the market source, input window and generation time, and separate historical input from generated future candles. If the evidence does not match what you see on the chart, do not follow the call.
7. **You are not borrowing another tool’s track record.** For example, do not use the 61.6% overall win rate checked on 2026-11-23 on the TradingView review to argue that this JEV or Kronos call is more trustworthy, and do not use one algorithm’s “backtest hit rate” to argue that an event contract will pay.

Even when all of the above appear to hold, that only means “the evidence is more consistent this time.” It is not proof the next trade will win, and it is not a reason to place an order immediately.

## Stand aside rather than order when any of these is true

Any one of the points below is enough to stay out. This is not a complete risk list — only the stop conditions that relate directly to these tools.

- The call is neutral, or the five-way probability mass is clearly spread out.
- You are reacting only to a high confidence figure, a high P(up), or a “strong” label, without checking the distribution, the evidence and the rules.
- Timeframes disagree, or the leading fusion weights are clearly fighting the liquidation map.
- The suggested stop sits in a liquidation cluster.
- You have not yet read the settlement price, expiry, payout or tie rule.
- The expiry is very short, random fluctuation matters more, and you have no extra independent evidence.
- The console reports incomplete data, or you are still logged out of Kronos and the analysis has not actually run.
- You are about to treat close error, a fusion backtest hit rate, or the historical win rate on the review page as the payout probability of *this* trade.
- The size is already larger than a total loss you can accept.

In those cases the right action is not to order, and to keep watching — not to hunt for a reason to “trust the model.”

## How this relates to the public win rate

If the question is “what is the live automated signal win rate?”, quote only the figures on the [TradingView signal review](https://coinpred.com/review), and say the window, that the page refreshes automatically, and that **the records do not stand in for JEV or Kronos results**. The snapshot checked on 2026-11-23, and how to read it, are in [How to read automated signal win rates](signals.md).

That ledger also does not authorise an event-contract order or a fused long/short call. Past win rates do not imply future results.

More detail: [fusion console](signal-lab.md) · [JEV and confidence](jev.md) · [Kronos forecasts](kronos.md) · [Event-contract forecasts](event-contracts.md) · [tutorial](https://coinpred.com/news/how-to-use/)

---

Questions or partnerships: Telegram [@DUCKS88896h](https://t.me/DUCKS88896h) · Email [3211caoq@gmail.com](mailto:3211caoq@gmail.com)
