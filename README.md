# 🏢 Bukhara Prime — Telegram Reklama Boti

Uy-joy kanallaridan reklamalarni olib, **Bukhara Prime** nomiga moslab kanalingizga yuboradigan bot.

---

## ⚡ O'rnatish (Setup)

### 1. Fayllarni yuklab oling
```bash
cd bukhara-prime-bot
npm install
```

### 2. `.env` faylini sozlang
```bash
cp .env.example .env
nano .env   # yoki VS Code bilan oching
```

`.env` ichiga quyidagilarni kiriting:
```env
BOT_TOKEN=7123456789:AAHxxxxxxxxxxxxxxxxxxxxxxxx
MY_CHANNEL=@bukhara_prime_kanal
SOURCE_CHANNELS=@tashkent_uylar,@buxoro_kvartira
COMPANY_NAME=Bukhara Prime
PHONE_NUMBER=+998905123444
ADMIN_ID=123456789
AUTO_POST_INTERVAL=60
```

### 3. Botni ishga tushiring
```bash
npm start
```

---

## 🔧 BOT_TOKEN olish

1. Telegramda **@BotFather** ni toping
2. `/newbot` yuboring
3. Bot nomini kiriting: `Bukhara Prime Bot`
4. Username kiriting: `bukhara_prime_bot`
5. Berilgan tokenni `.env` ga qo'ying

---

## 🆔 ADMIN_ID olish

1. Telegramda **@userinfobot** ga `/start` yuboring
2. U sizning ID ingizni ko'rsatadi
3. Shu raqamni `ADMIN_ID` ga qo'ying

---

## 📡 Kanallarni sozlash

### Bot manba kanalga admin bo'lishi shart!
Bot faqat **admin** yoki **member** bo'lgan kanallardan o'qiy oladi.

1. Manba kanal → Settings → Administrators → Botni qo'shing (faqat o'qish huquqi)
2. Maqsad kanal (`MY_CHANNEL`) → Botni **admin** qiling (post yuborish huquqi)

---

## 📱 Admin Buyruqlari

| Buyruq | Vazifasi |
|--------|----------|
| `/start` | Botni ishga tushirish |
| `/stats` | Statistikani ko'rish |
| `/pending` | Kutayotgan reklamalar |
| `/post_all` | Barchasini kanalga yuborish |
| `/add_channel @kanal` | Yangi manba kanal qo'shish |
| `/channels` | Kanallar ro'yxati |
| `/crm` | CRM baza ko'rish |

---

## 🔄 Qanday ishlaydi?

```
Manba kanal → Bot o'qiydi → Matnni o'zgartiradi → Bazaga saqlaydi → Kanalingizga yuboradi
```

1. **O'qish** — Manba kanaldan yangi reklama keladi
2. **Aniqlash** — Uy-joy reklamasimi tekshiradi
3. **O'zgartirish** — Kompaniya nomini va raqamni almashtiradi
4. **Saqlash** — CRM bazaga yozadi
5. **Yuborish** — Sizning kanalingizga yuboradi

---

## 🗄️ CRM Baza

Bot SQLite bazasi (`crm.db`) da saqlaydi:

- `ads` — barcha reklamalar (original + o'zgartirilgan)
- `source_channels` — manba kanallar
- `clients` — mijozlar

---

## ⚙️ Avtomatik Post

`AUTO_POST_INTERVAL=60` → har 60 daqiqada 3 ta reklama avtomatik yuboriladi.

`0` qo'ysangiz — faqat qo'lda yuboriladi.

---

## 🛠️ Muammo bo'lsa

**Bot yuklanmayapti:**
- `BOT_TOKEN` to'g'riligini tekshiring

**Kanal ko'rinmayapti:**
- Bot kanalga admin qilinganmi?
- Kanal username `@` bilan boshlanishi kerak

**Reklama yuborilmayapti:**
- `MY_CHANNEL` to'g'riligini tekshiring
- Botda kanal admin huquqi bormi?
