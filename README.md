# Bitcoin Technical Analysis Automation

Otomatik Bitcoin teknik analizi ve raporlama sistemi. n8n üzerinde çalışan bu workflow, Binance'ten canlı veri çekerek detaylı teknik analiz yapar ve AI destekli yorumlarla birlikte e-posta ve Google Sheets'e raporlar.

## 🎯 Özellikler

- **Otomatik Veri Toplama**: Binance public API'lerinden 4 saatte bir veri çeker
- **Kapsamlı Teknik Analiz**: SMA, EMA, RSI, MACD, Bollinger Bands, Stochastic, VWAP, ATR
- **AI Destekli Yorum**: DeepSeek R1 modeli ile detaylı piyasa analizi
- **Görsel Raporlama**: HTML formatında profesyonel e-posta raporları
- **Veri Arşivleme**: Google Sheets'te otomatik kayıt

## 📋 Gereksinimler

- n8n kurulumu (self-hosted veya cloud)
- Gmail hesabı (OAuth2 entegrasyonu)
- Google Sheets API erişimi
- OpenRouter API key (DeepSeek R1 modeli için)

**Not**: Binance API key **gerektirmez** - tüm veriler public endpoint'lerden çekilir.

## 🚀 Kurulum

1. **n8n Workflow'u İçe Aktarın**
   ```bash
   n8n import:workflow --input=BTC-Price-Report.json
   ```

2. **Credential'ları Yapılandırın**
   - Gmail OAuth2 (e-posta gönderimi için)
   - Google Sheets OAuth2 (veri kayıt için)
   - OpenRouter Bearer Token (AI analizi için)

3. **Workflow Ayarları**
   - `Schedule Trigger`: Çalışma sıklığını ayarlayın (varsayılan: 4 saat)
   - `Send a message`: E-posta alıcı adresini güncelleyin
   - `BTC Price Data`: Google Sheets döküman ID'sini ayarlayın

4. **Workflow'u Aktifleştirin**

## 🔧 Kullanılan API Endpoint'leri

```
GET https://api.binance.com/api/v3/ticker/24hr?symbol=BTCUSDT
GET https://api.binance.com/api/v3/klines?symbol=BTCUSDT&interval=4h&limit=180
POST https://openrouter.ai/api/v1/chat/completions
```

## 📊 Analiz Kapsamı

**Teknik İndikatörler:**
- Hareketli Ortalamalar: SMA(20,50,200), EMA(12,26), VWAP
- Momentum: RSI(14), Stochastic K, MACD
- Volatilite: Bollinger Bands, ATR(14)
- Destek/Direnç: Pivot Points, güncel seviyeler

**AI Analiz:**
- Piyasa durumu değerlendirmesi
- Kısa/orta vadeli görünüm
- Al-sat stratejisi önerileri
- Stop-loss ve take-profit seviyeleri
- Risk yönetimi tavsiyeleri

## 📧 Rapor Formatı

E-posta raporları şunları içerir:
- Piyasa özeti ve güncel fiyat
- Detaylı teknik indikatör tabloları
- AI destekli analiz ve strateji önerileri
- Kritik destek/direnç seviyeleri
- Görsel trend göstergeleri

## 📝 Lisans

MIT License

## ⚠️ Uyarı

Bu sistem yalnızca bilgilendirme amaçlıdır ve yatırım tavsiyesi niteliği taşımaz. Kripto para yatırımları yüksek risk içerir. Kendi araştırmanızı yapın ve risk yönetimi ilkelerini uygulayın.
