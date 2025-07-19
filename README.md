# 🤖 MHRS Takip Botu

MHRS Takip Botu, Türkiye’deki **MHRS (Merkezi Hekim Randevu Sistemi)** üzerinden randevuları otomatik olarak takip eden bir Telegram botudur.  
Belirlediğiniz il, ilçe, klinik ve tarih aralığı için boş randevu bulunursa sizi **Telegram’dan bildirir** veya isterseniz **otomatik randevu alır**.

---

## ✨ Özellikler

✅ **Boş randevu bulunca Telegram’dan bildirir**  
✅ **İsteğe bağlı otomatik randevu alabilir**  
✅ **Tarih aralığı seçebilme**  
✅ **Kolay kurulum ve kullanım**  

---

## 🔧 Kurulum

1️⃣ **Python 3.10+ kurulu olmalı**  
Windows’ta [Python indir](https://www.python.org/downloads/)

2️⃣ **Gerekli kütüphaneleri yükle**

```bash
pip install -r requirements.txt
```

3️⃣ **Telegram Bot Token’ini ayarla**  
Aşağıda anlatacağım şekilde bir Telegram bot token’i al ve `mhrs.py` içine ekle:

```python
app = ApplicationBuilder().token("TELEGRAM_BOT_TOKEN_BURAYA").build()
```

4️⃣ **Botu çalıştır**

```bash
py -3.10 mhrs.py
```

Bot çalışınca terminalde **📡 Bot çalışıyor…** yazacak.

---

## 🤖 Telegram Bot Token Nasıl Alınır?

Telegram botun MHRS sistemini kullanıcılara ulaştırabilmesi için bir **bot token** gerekiyor.  
Bu token’i **BotFather** üzerinden kolayca alabilirsin:

1. Telegram’da [@BotFather](https://t.me/BotFather) hesabına gir  
2. `/start` yaz ve gönder  
3. `/newbot` yaz ve yeni bot oluştur  
4. BotFather senden **bot ismi** ve **kullanıcı adı** isteyecek  
5. Sonunda sana şu formatta bir token verecek:

```
1234567890:AAH-R7vyraom5aDQrgkZEJJZ08Bc1XUJ-CY
```

6. Bu token’i `mhrs.py` dosyasındaki şu kısma yapıştır:

```python
app = ApplicationBuilder().token("BURAYA_TOKEN_YAZ").build()
```

Ve botun hazır!

---

## 🏥 MHRS Token Nasıl Alınır?

MHRS token, botun senin adına randevu işlemi yapabilmesi için gerekiyor. İki farklı şekilde alabilirsin:

### 📱 Mobil Uygulama ile (HttpCanary)

1. Telefonuna **HttpCanary** uygulamasını indir  
2. MHRS mobil uygulamasına giriş yap  
3. HttpCanary üzerinden `/kurum-rss` isteğini bul  
4. İçinde **Authorization: Bearer xxxxx** şeklinde bir değer olacak  
5. Bu değeri bot’a gönder

### 💻 Web Tarayıcı ile

1. [MHRS](https://www.mhrs.gov.tr) sitesine gir ve giriş yap  
2. **F12** ile geliştirici konsolu aç  
3. **Network** sekmesinde bir istek seç  
4. **Headers** kısmında `Authorization` satırını bul  
5. **Bearer xxxxxxx** şeklindeki değeri kopyala ve bot’a gönder

---

## 🚀 Kullanım

1️⃣ Telegram’da botu başlat:
```
/start
```

2️⃣ MHRS token’ını gönder

3️⃣ İl, ilçe, klinik, tarih aralığı ve mod (otomatik/bildirim) seç

4️⃣ Bot senin için randevu bulunca **mesaj atar** veya **otomatik alır**

---

## 🛠 Olası Hatalar ve Çözümleri

### ❌ `TypeError: AsyncClient.__init__() got an unexpected keyword argument 'proxies'`

Bu hata **python-telegram-bot** ve **httpx** kütüphaneleri sürüm uyumsuz olduğunda oluşur.  
Çözmek için:

```
pip install --force-reinstall httpx==0.27.0
```

Bu sayede `httpx.AsyncClient` eski API’yi destekleyecek ve hata düzelecek.

---

## 🛠 Geliştirici

👤 **Akın**   
💻 GitHub: [4kinn](https://github.com/4kinn)

---

## 📌 Not

Bu bot tamamen **eğitim ve otomasyon amaçlıdır**. MHRS’nin resmi servisi değildir.
