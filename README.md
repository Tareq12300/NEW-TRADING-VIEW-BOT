# Stoch RSI + MACD 4H Bot — No Pandas

بوت تيليجرام يفحص أزواج USDT على عدة منصات باستخدام CCXT، ويعتمد فقط على:

- Stochastic RSI
- MACD
- فريم 4H

## Railway Variables

انسخ من `.env.example` وضع القيم في Railway Variables.

أهم القيم:

```env
TELEGRAM_BOT_TOKEN=
TELEGRAM_CHAT_ID=
TIMEFRAME=4h
EXCHANGES=binance,bybit,okx,bitget,mexc,gateio,kucoin
STOCH_MAX=40
REQUIRE_STOCH_CROSS=true
REQUIRE_MACD_POSITIVE=true
REQUIRE_MACD_HISTOGRAM_UP=true
```

## Start command

```bash
python bot.py
```

## ملاحظات

- لا يستخدم pandas.
- لا يستخدم DexScreener.
- لا يستخدم CoinGecko.
- يعتمد فقط على ccxt + numpy.


## Volume filter

The bot filters pairs with 24h quote volume below 100,000 USDT by default using `MIN_DAILY_VOLUME_USDT=100000`.
