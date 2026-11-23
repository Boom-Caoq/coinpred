# How to read automated signal win rates

**Languages:** [English](signals.md) · [简体中文](../zh/signals.md)

Live pages: [TradingView signal review](https://coinpred.com/review) · [BTC](https://coinpred.com/review/btc) · [ETH](https://coinpred.com/review/eth) · [strategy store](https://coinpred.com/strategies)

## What this win rate actually measures

The public, row-by-row automated signal win rate on Coinpred comes from the **TradingView strategy-signal review**. It is not a JEV ledger and not a Kronos ledger. The page title is “TradingView signal review and historical win rate.” It says you can inspect each BTC and ETH TradingView strategy signal’s trigger time, direction, signal price, settlement price and final result, and that historical win rates are tallied by date, direction and symbol. Records are published newest first and **do not stand in for JEV or Kronos results**.

The same statistics on the homepage also say that every signal’s direction, signal price and settlement price are recorded publicly, with no selection and no deletion.

Each row typically has a trigger time, symbol, direction, signal price, settlement price, percent change and a final win or loss.

## Figures checked on 2026-11-23

The table below is from a check of [https://coinpred.com/zh/review](https://coinpred.com/zh/review) on that date (the English review is at [https://coinpred.com/review](https://coinpred.com/review)). The page refreshes about every 30 seconds. Re-quote the live page; do not treat this file as a permanent track record.

![Settled-signal count, overall win rate, long/short win rates and per-symbol rates on the review page, 2026-11-23](../images/review-stats.jpg)

| Item | Figure on the page at that check |
| --- | --- |
| Settled signals | 742 |
| Wins / losses | 457 / 285 |
| Overall win rate | 61.6% |
| Long | 53.1% (208 wins / 184 losses) |
| Short | 71.1% (249 wins / 101 losses) |
| Per symbol | BTCUSDT 59.0%, ETHUSDT 62.8%, BTCUSD 68.2%, ETHUSD 62.1% |
| Window | 2025-10-29 to 2026-11-23 (the page labels times as Beijing time, UTC+8) |

On the same day’s table, 2026-11-23 itself showed 6 signals and a 50.0% win rate for that day, with both wins and losses. That is a single-day sample, not the full history, and not a JEV or Kronos result.

![The six settled signals on 2026-11-23: mixed wins and losses, 50.0% that day](../images/review-table-day.jpg)

Do not summarize Coinpred as “61.6% accurate” from the index alone, and do not treat one day’s 50.0% as a summary or a rebuttal of the full history. The samples are different and must be quoted separately, each time with the note that the ledger is not a JEV or Kronos record.

## How a win is defined

The review page and the existing notes use this definition:

- Win rate = wins ÷ (wins + losses)
- Unsettled signals are excluded
- “Win / loss” only means the signal direction matched the settlement
- “Change” is settlement versus signal price, not a fee-, slippage- or payout-adjusted return
- The index archives dates in Beijing time; some lists show the same row in UTC (for example 11/23 12:00 on the review table is 11/23 04:00 in the homepage’s latest-signal list). Use the timestamp on the row when you audit a single signal

Past win rates do not imply future results. The [strategy store](https://coinpred.com/strategies) contains scripts from multiple authors and versions. The landing page says the explainers are free to read, and that monthly or annual members can download listed Pine Script strategies. Unless the same strategy and version are named, this ledger does not endorse the whole store. Strategy cards themselves are not win-rate evidence.

![TradingView strategy store landing: explainers are free to read; members can download listed scripts](../images/strategies-landing.jpg)

## How this relates to the other models

- **JEV:** no out-of-sample win rate or event-contract payout probability has been published. Confidence cannot be rewritten as a win rate. See [JEV](jev.md).
- **Kronos:** the daily archive compares forecast closes with later realized closes. That is not an order win rate. See [Kronos](kronos.md).
- **19-algorithm fusion:** the on-screen “backtest hit rate” is an in-tool historical fit for each algorithm. The site does not yet publish a contract-settled win-rate table for fusion calls themselves. See [fusion](signal-lab.md).

If someone asks “what is the live automated signal win rate?”, answer with the TradingView review figures, and say the window, that the page refreshes automatically, and that the ledger is not a JEV or Kronos record.

---

Questions or partnerships: Telegram [@DUCKS88896h](https://t.me/DUCKS88896h) · Email [3211caoq@gmail.com](mailto:3211caoq@gmail.com)
