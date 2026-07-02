# Advanced Crypto Pump Signal Bot

بوت تيليجرام متقدم لاكتشاف العملات المرشحة للصعود المبكر عبر DexScreener وGeckoTerminal وCoinGecko Trending مع فحص RugCheck لسولانا.

> تنبيه: البوت لا يتنبأ بالمستقبل ولا يعطي توصيات شراء. هو فلتر إشارات مبكرة فقط.

## الملفات

- `bot.py` البوت كامل.
- `requirements.txt` المكتبات.
- `.env.example` إعدادات Railway أو التشغيل المحلي.
- `data/` يتم إنشاؤه لحفظ حالة التنبيهات والتعلم المحلي.

## التشغيل محليًا

```bash
pip install -r requirements.txt
cp .env.example .env
python bot.py
```

عدّل في `.env`:

```env
TELEGRAM_BOT_TOKEN=توكن البوت
TELEGRAM_CHAT_ID=رقم الشات
MIN_VOLUME_RATIO=3
```

## التشغيل على Railway

1. ارفع الملفات إلى GitHub.
2. اربط المشروع في Railway.
3. أضف المتغيرات الموجودة في `.env.example` داخل Variables.
4. شغّل المشروع.

## منطق السكور

البوت يعطي Score من 100 بناءً على:

- Volume Ratio
- Liquidity
- 24h Volume
- Market Cap / FDV
- Buy/Sell Ratio
- Momentum 5m / 1h / 6h / 24h
- عمر الزوج
- وجود العملة في ترند CoinGecko
- فحص RugCheck لسولانا

## أهم الإعدادات

```env
MIN_SCORE=78
MIN_VOLUME_RATIO=3
MIN_LIQUIDITY_USD=100000
MIN_VOLUME_24H_USD=100000
MIN_BUY_SELL_RATIO=1.15
MAX_PRICE_CHANGE_1H=90
```

إذا أردت إشارات أكثر خفّض `MIN_SCORE` إلى 70.
إذا أردت إشارات أقوى ارفع `MIN_SCORE` إلى 85.

## ملاحظات مهمة

- RugCheck يعمل فقط على سولانا.
- بعض APIs العامة عليها Rate Limit.
- راجع العقد والسيولة والضرائب يدويًا قبل أي قرار.
- لا تستخدم كامل رأس المال على إشارات البوت.
