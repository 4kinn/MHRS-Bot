# MHRS Telegram Takip Botu

MHRS (Merkezi Hekim Randevu Sistemi) üzerinden randevu takibi yapmanızı sağlayan Telegram botudur.  
Telegram üzerinden MHRS tokenınızı girerek istediğiniz klinik ve tarih aralığında otomatik veya bildirim amaçlı randevu takibi yapabilirsiniz.

---

## Özellikler

- MHRS token ile kolay giriş  
- İl, ilçe ve klinik seçimi  
- Otomatik randevu alma veya sadece bildirim alma seçeneği  
- Takip edilen randevuları durdurma  
- Basit ve hızlı kullanım  

---

## Gereksinimler

- Python 3.10 veya üzeri  
- `python-telegram-bot` paketi  
- `requests` paketi  

---

## Kurulum

1. Python yüklü değilse [python.org](https://www.python.org/downloads/) (3.10 tavsiye edilir) adresinden indirip kurun.  
2. Terminal veya komut istemcisine aşağıdaki komutu girerek gerekli kütüphaneleri yükleyin:

```bash
pip install python-telegram-bot requests
