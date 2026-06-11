# 🦁 Trading AI Beast V3

> Autonomous trading signal system — crypto + stocks, 40 assets, ML-powered, Telegram delivery.

---

## 🇬🇧 English

### What It Does

Trading AI Beast V3 collects market data, news, and on-chain signals every day, trains a stacking ML ensemble, and sends BUY / WAIT signals with stop-loss, take-profit, and Kelly-sized position recommendations straight to your Telegram.

### Features

- **Stacking ensemble** — LightGBM + XGBoost + GradientBoosting + RandomForest + ExtraTrees unified by a Logistic Regression meta-learner
- **Optuna hyperparameter tuning** — 50 Bayesian trials per asset, every run
- **Purged Walk-Forward CV** — 7-day embargo gap between train and test, zero data leakage
- **Temporal weighting** — recent data weighted up to 5× more than old data
- **FinBERT sentiment** — 22 RSS feeds + 5 news APIs analyzed by a financial BERT model
- **On-chain signals** — funding rates, open interest, orderbook imbalance, mempool congestion
- **130+ features** — trend, momentum, volatility, volume, macro, correlation, seasonality
- **Half-Kelly + portfolio cap** — position sizing that protects your account
- **Dynamic SL/TP** — stop and target adapt to current ATR and volatility regime
- **Live accuracy tracking** — yesterday's signals verified against real prices daily
- **Telegram bot** — signals at 06:00, 10:00, 14:00, 18:00, 22:00

### Assets Covered

**Crypto (20):** Bitcoin, Ethereum, Solana, Cardano, Avalanche, Chainlink, Polkadot, Uniswap, Litecoin, Stellar, Dogecoin, Shiba Inu, Polygon, NEAR, Cosmos, Tron, Algorand, VeChain, Fantom, The Sandbox

**Stocks (20):** AAPL, TSLA, NVDA, MSFT, GOOGL, AMZN, META, AMD, COIN, NFLX, JPM, BAC, V, MA, PYPL, UBER, SPOT, SQ, PLTR, HOOD

### Tech Stack

| Layer | Tools |
|---|---|
| ML Models | LightGBM, XGBoost, scikit-learn, Optuna |
| NLP | FinBERT (Hugging Face Transformers) |
| Market Data | CoinGecko, yFinance (Yahoo Finance) |
| On-Chain | Binance Futures API, Mempool.space |
| News | NewsAPI, GNews, Guardian, Currents, MediaStack, 22× RSS |
| Technical Analysis | `ta` library (130+ indicators) |
| Storage | Google Drive, Parquet, CSV |
| Delivery | Telegram Bot API |
| Runtime | Google Colab (free GPU) |

### Setup & Usage

1. Open `TradingAI_BEAST_V3.ipynb` in Google Colab
2. Run **Step 0** once to clear old data
3. Run **Steps 1–14** every day in order
4. Run **Step 15** last if you want 24/7 auto mode

> **Step 15 keeps the Colab session alive and sends signals automatically on schedule. Keep the browser tab open.**

### Configuration

Edit **Step 2** to change:

```python
SIGNAL_THRESHOLD = 68    # minimum confidence % to show signal
MIN_ACCURACY     = 0.55  # minimum model accuracy to include asset
OPTUNA_TRIALS    = 50    # more trials = better tuning, slower run
MAX_KELLY_FRAC   = 0.20  # max single position size (fraction of capital)
```

### Output Example (Telegram)

```
🦁 Trading AI BEAST V3 — 11.06.2025 10:00
Fear&Greed: 42/100 — 😨 Страх
Sentiment: -0.124 | Δ7d: +0.031
Model accuracy: 56.2%

📈 BUY / GROWTH

ETHEREUM [crypto] — $3,412.50 [📊IND✓]
  🔥🔥 71% confidence | ✅ accuracy 57.3%
  RSI:34 | Indicators:68% | Sent:+0.18
  Kelly: 8.4% | R/R: 2.3x
  🛑 Stop: $3,198.00  🎯 Target: $3,890.00
  ⏱ 3–7 days | 📈 Oversold — recovery expected
```

### Important Disclaimer

> This is not financial advice. The system provides signals based on statistical patterns — past performance does not guarantee future results. Always manage your own risk. Never risk more than you can afford to lose.

---

## 🇷🇺 Русский

### Что это такое

Trading AI Beast V3 — это автономная система торговых сигналов. Каждый день она собирает рыночные данные, новости и on-chain метрики, обучает ансамблевую ML-модель и отправляет сигналы BUY / WAIT со стоп-лоссом, тейк-профитом и рекомендацией размера позиции прямо в Telegram.

### Возможности

- **Stacking-ансамбль** — LightGBM + XGBoost + GradientBoosting + RandomForest + ExtraTrees с мета-моделью Logistic Regression
- **Optuna** — 50 байесовских trials на каждый актив, автоматический подбор гиперпараметров
- **Purged Walk-Forward CV** — 7-дневный embargo gap между обучением и тестом, нулевая утечка данных
- **Temporal weighting** — свежие данные весят до 5× больше старых
- **FinBERT** — финансовая BERT-модель анализирует 22 RSS-ленты и 5 новостных API
- **On-chain сигналы** — funding rates, open interest, дисбаланс стакана, загрузка mempool
- **130+ признаков** — тренд, моментум, волатильность, объём, макро, корреляция, сезонность
- **Half-Kelly + портфельный лимит** — управление позицией, которое защищает депозит
- **Динамические SL/TP** — стоп и цель адаптируются к текущему ATR и волатильности
- **Живой трекинг точности** — вчерашние сигналы каждый день сверяются с реальными ценами
- **Telegram-бот** — сигналы в 06:00, 10:00, 14:00, 18:00, 22:00

### Покрытые активы

**Крипта (20):** Bitcoin, Ethereum, Solana, Cardano, Avalanche, Chainlink, Polkadot, Uniswap, Litecoin, Stellar, Dogecoin, Shiba Inu, Polygon, NEAR, Cosmos, Tron, Algorand, VeChain, Fantom, The Sandbox

**Акции (20):** AAPL, TSLA, NVDA, MSFT, GOOGL, AMZN, META, AMD, COIN, NFLX, JPM, BAC, V, MA, PYPL, UBER, SPOT, SQ, PLTR, HOOD

### Технологический стек

| Слой | Инструменты |
|---|---|
| ML-модели | LightGBM, XGBoost, scikit-learn, Optuna |
| NLP | FinBERT (Hugging Face Transformers) |
| Рыночные данные | CoinGecko, yFinance (Yahoo Finance) |
| On-chain | Binance Futures API, Mempool.space |
| Новости | NewsAPI, GNews, Guardian, Currents, MediaStack, 22× RSS |
| Технический анализ | библиотека `ta` (130+ индикаторов) |
| Хранение | Google Drive, Parquet, CSV |
| Доставка | Telegram Bot API |
| Среда | Google Colab (бесплатный GPU) |

### Установка и запуск

1. Открой `TradingAI_BEAST_V3.ipynb` в Google Colab
2. Запусти **ШАГ 0** один раз для очистки старых данных
3. Запускай **ШАГи 1–14** каждый день по порядку
4. Запусти **ШАГ 15** последним, если нужен 24/7 авторежим

> **ШАГ 15 держит сессию Colab активной и отправляет сигналы автоматически по расписанию. Оставь вкладку браузера открытой.**

### Настройка

Отредактируй **ШАГ 2** под себя:

```python
SIGNAL_THRESHOLD = 68    # минимальная уверенность (%) для отображения сигнала
MIN_ACCURACY     = 0.55  # минимальная точность модели для включения актива
OPTUNA_TRIALS    = 50    # больше trials = лучше тюнинг, дольше работает
MAX_KELLY_FRAC   = 0.20  # максимальный размер позиции (доля капитала)
```

### Пример вывода в Telegram

```
🦁 Trading AI BEAST V3 — 11.06.2025 10:00
Fear&Greed: 42/100 — 😨 Страх
Sentiment: -0.124 | Δ7d: +0.031
Ср.точность модели: 56.2%

📈 ПОКУПАТЬ / РОСТ

ETHEREUM [крипта] — $3,412.50 [📊IND✓]
  🔥🔥 71% уверенность | ✅ точность 57.3%
  RSI:34 | Индик:68% | Sent:+0.18
  Kelly: 8.4% | R/R: 2.3x
  🛑 Стоп: $3,198.00  🎯 Цель: $3,890.00
  ⏱ 3–7 дней | 📈 Перепродан — ожидаем восстановление
```

### Важный дисклеймер

> Это не финансовый совет. Система генерирует сигналы на основе статистических паттернов — прошлые результаты не гарантируют будущую прибыль. Всегда управляй риском самостоятельно. Не рискуй деньгами, которые не можешь позволить себе потерять.

---

*Built with ❤️ and way too much coffee.*
