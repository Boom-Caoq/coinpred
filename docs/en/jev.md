# How JEV works, and what confidence means

**Languages:** [English](jev.md) · [简体中文](../zh/jev.md)

Canonical page: [JEV model notes](https://coinpred.com/news/jev-model/) (updated 2026-10-26).

JEV answers “which way does the evidence lean right now?” It is not a candle generator and not a TradingView strategy signal.

## What the model is based on

JEV is a [TypeSafe AI](https://typesafe.ai/) System One model. It takes a context window and predefined questions, and returns structured results a program can use: a Choice, a Score, and probabilities. TypeSafe describes the training method as **RLCD** (Reinforcement Learning for Calibrated Decisions), with an emphasis on decisions and uncertainty.

Source: [TypeSafe · Introducing Jev](https://typesafe.ai/blog/introducing-system-one-models-and-jev) (reviewed on the site as of 2026-09-23).

Unlike a general-purpose model that writes a long essay, JEV may only pick among the options we define, and it must attach a probability to each option. That makes the output easier to display consistently and to check later.

## What each request contains

After you click “Start analysis”, Coinpred’s server assembles a structured market context. The product rule is: **compute indicators in code, leave the synthesis to the model**. TypeSafe also documents limitations around numerical precision and complex indirect reasoning, which is why indicators are precomputed. [JEV 1.13 known limitations](https://docs.typesafe.ai/model-jaggedness/jev-1.13)

1. **200 historical candles and volume** (Binance spot; the timeframe is yours: 1m, 5m, 15m, 1h, 4h, 1d).
2. **12 program-computed indicators**
   - Trend: EMA20, EMA50, SMA200, ADX
   - Momentum: RSI(14), MACD(12, 26, 9), Stochastic(14, 3), CCI(20), Williams %R(14)
   - Volatility: ATR(14), Bollinger(20, 2)
   - Volume: OBV
3. **Live book depth** (top 15 WEEX bids and asks).
4. **Recent trades** on WEEX, used to see aggressive buying versus selling.

Two boundaries matter:

- The inputs describe **spot** markets. The candle interval is a resolution, **not** an event-contract expiry.
- The request does **not** bind a specific strike, settlement rule or payout, so the output is technical context only.

## The five directions

| Direction | Criterion (summary) |
| --- | --- |
| Strongly bullish | Trend, momentum, the book and recent trades strongly agree to the upside |
| Bullish | Evidence leans up, with some disagreement or missing confirmation |
| Neutral | Evidence is mixed, weak or conflicting; no reliable edge |
| Bearish | Evidence leans down, with some disagreement or missing confirmation |
| Strongly bearish | Trend, momentum, the book and recent trades strongly agree to the downside |

Neutral is a valid answer. When the evidence conflicts, the model is allowed — and encouraged — to say the picture is unclear.

## What the confidence model is

TypeSafe’s public guide says Choice and Score return a probability distribution over the options, and a **0–1 confidence** is derived from that distribution: more concentrated means a clearer decision, more spread means more uncertainty. [TypeSafe · Confidence](https://docs.typesafe.ai/confidence)

Keep these distinctions:

- The official docs **do not publish the exact formula**, so this page does not present “top-choice probability” or “entropy” as the official algorithm.
- Coinpred displays the direction answer’s `confidence × 100%`, or “—” when the model returns none.
- **Direction confidence**, **confidence on a separate score question**, and **the largest direction probability** are three different quantities.

## Confidence is not a win rate

This is the site’s own wording, and the most important one:

**Directional confidence measures how certain this classification is. It is not an event-contract win probability.** An 80% reading does not mean that class of trades has an 80% historical win rate.

A real win rate would need a fixed forecast time, expiry rule and settlement price, out-of-sample tests, baselines, calibration curves and Brier scores, plus costs and payouts. **Coinpred has not published that JEV validation.**

Do not place an order just because confidence is high. Confidence tells you whether this probability mass is concentrated. It does not tell you how often that kind of trade has paid.

## Where the evidence and guidance come from

JEV does not write a free-form report.

- “Evidence” is assembled by the application from the input data — for example price versus moving averages, a MACD turn, or book imbalance.
- “Observation guidance” is chosen from a preset list (wait for confirmation, watch a pullback, contain downside risk, watch resistance, stay neutral) and then mapped to preset copy.

These **are not the model’s internal chain of thought**. If you use a JEV call as a second opinion, look at the shape of the distribution first, then check whether the assembled evidence matches what you see on the chart.

## How to use it

- Treat JEV as a structured second opinion, not a trade signal.
- A concentrated distribution means the evidence is more consistent; a spread-out distribution means the tape itself is unclear.
- Decide only after you know your expiry, payout and size limits.
- If you also use the fusion console and liquidation map, still follow the [decision checklist](decision.md).

See also: [tutorial](https://coinpred.com/news/how-to-use/) · [BTC event contracts](https://coinpred.com/news/btc-event-contracts/) · [Automated signal win rates](signals.md)

---

Questions or partnerships: Telegram [@DUCKS88896h](https://t.me/DUCKS88896h) · Email [3211caoq@gmail.com](mailto:3211caoq@gmail.com)
