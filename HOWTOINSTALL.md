<div align="center">
  <h1>🛠️ HOW TO INSTALL</h1>
  <p><strong>WhatsApp Recovery Bot — Panduan Instalasi & Konfigurasi</strong></p>
  <p><em>Untuk pembeli script — follow langkah di bawah.</em></p>
</div>

---

## 📋 Daftar Isi

- [Persyaratan](#-persyaratan)
- [Langkah 1: Install Node.js](#-langkah-1-install-nodejs)
- [Langkah 2: Ekstrak Script](#-langkah-2-ekstrak-script)
- [Langkah 3: Install Dependencies](#-langkah-3-install-dependencies)
- [Langkah 4: Buat Bot Telegram](#-langkah-4-buat-bot-telegram)
- [Langkah 5: Konfigurasi .env](#-langkah-5-konfigurasi-env)
- [Langkah 6: Buat Channel Telegram](#-langkah-6-buat-channel-telegram)
- [Langkah 7: Setup Saweria (Opsional)](#-langkah-7-setup-saweria-opsional)
- [Langkah 8: Setup Database Cloud](#-langkah-8-setup-database-cloud)
- [Langkah 9: Jalankan Bot](#-langkah-9-jalankan-bot)
- [Maintenance](#-maintenance)
- [Troubleshooting](#-troubleshooting)

---

## ✅ Persyaratan

| Komponen | Minimal |
|----------|---------|
| **Node.js** | 18+ (LTS direkomendasikan) |
| **RAM** | 512 MB |
| **Storage** | 250 MB |
| **OS** | Windows 10+, Linux (Ubuntu/Debian), macOS |
| **Koneksi** | Internet stabil (untuk polling Telegram & email) |

> 💡 **Rekomendasi:** VPS Ubuntu 22.04 — 1 CPU / 1 GB RAM (Rp50-100k/bulan).

---

## 📦 Langkah 1: Install Node.js

<details>
<summary><b>🐧 Linux (Ubuntu/Debian)</b></summary>

```bash
# Download & install Node.js 18 LTS
curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
sudo apt-get install -y nodejs

# Verifikasi
node -v   # harus >= v18
npm -v
```
</details>

<details>
<summary><b>🪟 Windows</b></summary>

1. Buka https://nodejs.org (download LTS v18+)
2. Jalankan installer — klik Next sampai selesai
3. Buka **Command Prompt** atau **PowerShell**, verifikasi:
```bash
node -v   # harus >= v18
npm -v
```
</details>

<details>
<summary><b>🍎 macOS</b></summary>

```bash
# Via Homebrew
brew install node@18
node -v
npm -v
```
</details>

---

## 📂 Langkah 2: Ekstrak Script

Extract file `.zip` atau `.rar` yang kamu terima ke direktori tujuan:

```bash
# Contoh Linux:
unzip whatsapp-recovery-bot.zip -d /home/user/bot
cd /home/user/bot

# Contoh Windows:
# Extract via WinRAR / 7-Zip ke D:\TelegramBot
cd D:\TelegramBot
```

---

## 📥 Langkah 3: Install Dependencies

```bash
npm install
```

Perintah ini akan membaca `package.json` dan menginstall semua modul yang dibutuhkan.

**Modules yang akan terinstall:**

| Module | Fungsi |
|--------|--------|
| `node-telegram-bot-api` | Koneksi ke Telegram Bot API |
| `@whiskeysockets/baileys` | WhatsApp Multi-Device (pairing code, cek nomor) |
| `nodemailer` | Kirim email ke support WhatsApp |
| `axios` | HTTP requests (Saweria payment, WA API) |
| `cheerio` | Scrape Saweria user ID |
| `dotenv` | Baca file `.env` |
| `pino` + `pino-pretty` | Logging (rapi & warna) |
| `@supabase/supabase-js` | Cloud backup (opsional — PostgreSQL) |
| `mongodb` | Cloud backup (opsional — MongoDB Atlas) |

---

## 🤖 Langkah 4: Buat Bot Telegram

1. Buka Telegram, cari **[@BotFather](https://t.me/BotFather)**
2. Kirim perintah:
   ```
   /newbot
   ```
3. Ikuti petunjuk:
   - **Nama bot** — bebas (contoh: `My Recovery Bot`)
   - **Username bot** — harus unik, akhiri `bot` (contoh: `MyRecoveryBot`)
4. Simpan **Bot Token** yang diberikan BotFather:
   ```
   1234567890:AAFdK...token...abc
   ```
5. (**Opsional**) Set foto profil bot via BotFather:
   ```
   /setuserpic
   ```
6. (**Opsional**) Tambahkan bot ke channel yang akan dijadikan **REQUIRED_CHANNEL** (lihat Langkah 6) sebagai **Administrator** minimal dengan hak "Send Messages"

---

## ⚙️ Langkah 5: Konfigurasi .env

Buka file `.env` di folder script dan isi konfigurasinya:

```env
# Telegram Bot
BOT_TOKEN=1234567890:AAFdK...token...abc
DEVELOPER_ID=8704394150    # Ganti dengan ID Telegram kamu

# Email (Gmail App Password)
EMAIL_USER=emailkamu@gmail.com
EMAIL_PASS=abcd efgh ijkl mnop    # App Password 16 karakter (dengan spasi)

# Gmail App Password → https://myaccount.google.com/apppasswords
# (Aktifkan 2FA dulu, lalu buat App Password > Mail > Windows)

# Optional fallback email (server cadangan)
FALLBACK_EMAIL_USER=
FALLBACK_EMAIL_PASS=

# Channel verification
REQUIRED_CHANNEL_USERNAME=@channelkamu
REQUIRED_CHANNEL_ID=-1001234567890
REQUIRED_CHANNEL2_USERNAME=@channelkamu2
REQUIRED_CHANNEL2_ID=-1001234567891

# Logging — kirim notifikasi ke channel (bisa pakai channel yang sama)
LOG_CHANNEL_ID=-1001234567890

# Saweria (payment gateway)
SAWERIA_USERNAME=usernamesaweriamu
```

> 💡 **Cek ID Channel/User:** Forward pesan ke [@userinfobot](https://t.me/userinfobot) di Telegram

---

## 📢 Langkah 6: Buat Channel Telegram

1. Buat **channel publik** di Telegram (bisa public atau private)
2. Tambahkan bot sebagai **Administrator** channel tersebut dengan minimal hak "Send Messages"
3. Masukkan username channel dan ID ke `.env`:
   ```env
   REQUIRED_CHANNEL_USERNAME=@namachannel
   REQUIRED_CHANNEL_ID=-100xxxxxxxxx
   ```

> 🔄 Bisa menggunakan 1 atau 2 channel. Cukup kosongkan `REQUIRED_CHANNEL2_*` jika tidak dipakai.

---

## 💳 Langkah 7: Setup Saweria (Opsional)

Untuk menerima pembayaran QRIS (VIP Premium):

1. Daftar di [saweria.co](https://saweria.co)
2. Buat halaman donasi
3. Catat **username Saweria** kamu (dari URL: `saweria.co/namauser`)
4. Masukkan ke `.env`:
   ```env
   SAWERIA_USERNAME=namauser_kamu
   ```

---

## ☁️ Langkah 8: Setup Database Cloud

Bot mendukung backup ke **Supabase (PostgreSQL)** dan/atau **MongoDB Atlas** secara fire-and-forget.
Data tetap aman di file JSON lokal — cloud hanya backup.

---

### ☁️ Opsi A: Supabase (PostgreSQL)

1. Daftar di [supabase.com](https://supabase.com) (Free tier 500MB)
2. Buat project baru
3. Buka **Project Settings → API**
4. Salin:
   - **Project URL** → `SUPABASE_URL`
   - **service_role key** (JANGAN anon key!) → `SUPABASE_SERVICE_KEY`
5. Buka **SQL Editor**, paste & jalankan isi file `supabase-migration.sql`
6. Masukkan ke `.env`:
   ```env
   SUPABASE_URL=https://xxxxx.supabase.co
   SUPABASE_SERVICE_KEY=eyJhbGciOiJ...token...abc
   ```

---

### ☁️ Opsi B: MongoDB Atlas (NoSQL)

1. Daftar di [mongodb.com/atlas](https://mongodb.com/atlas) (Free tier 512MB)
2. Buat **Free M0 Cluster**
3. Di tab **Security**:
   - **Database Access** → Add database user (username & password)
   - **Network Access** → Add IP `0.0.0.0/0` (allow all) atau IP VPS kamu
4. Klik **Connect → Drivers** → Copy connection string
5. Masukkan ke `.env`:
   ```env
   MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/?appName=BotTele
   ```

> 💡 **Keduanya opsional.** Bot jalan tanpa cloud backup — data tetap aman di file JSON lokal.
> Tapi sangat disarankan untuk memiliki minimal satu cloud backup agar data tidak hilang jika VPS rusak.

---

## 🚀 Langkah 9: Jalankan Bot

```bash
npm start
```

**Output sukses:**
```
{"level":30,"msg":"BOT STARTED"}
{"level":30,"msg":"Cloud sync complete"}
```

**Untuk menjalankan di background (Linux VPS):**
```bash
# Install PM2
npm install -g pm2

# Jalankan dengan PM2
pm2 start index.js --name whatsapp-bot

# Auto-start saat reboot
pm2 startup
pm2 save

# Lihat log
pm2 logs whatsapp-bot
```

**Untuk menjalankan di Windows:**
- Buka Command Prompt / PowerShell, jalankan `npm start`
- Biarkan terminal tetap terbuka
- Atau gunakan **Node.js wrapper** seperti `pm2` atau `node-windows`

---

## 🔧 Maintenance

### Update Script

Kamu mendapat update gratis. Jika ada versi baru:

1. Extract file update (timpa folder yang lama)
2. **Jangan** timpa file `.env` (konfigurasi kamu akan hilang)
3. Install ulang dependencies jika ada module baru:
   ```bash
   npm install
   ```
4. Restart bot

### Backup Data

Data bot ada di file JSON di folder utama bot. Backup file-file ini secara berkala:

- `users.json`, `premium.json`, `owners.json`
- `devices.json`, `donated_servers.json`
- `referrals.json`, `purchases.json`, `rate-limit-state.json`
- Folder `data/` (sent emails log)

Jika pakai Supabase dan/atau MongoDB, data otomatis tersync ke cloud.

### Cek Log

```bash
# Mode development (log warna)
NODE_ENV=development npm start  # atau: set NODE_ENV=development && npm start (Windows)
```

---

## ❌ Troubleshooting

| Masalah | Solusi |
|---------|--------|
| `BOT_TOKEN is empty` | Isi `BOT_TOKEN` di `.env` |
| `Cannot find module 'xxx'` | Jalankan `npm install` |
| `Port already in use` | Tutup proses bot lama (task manager / `kill`) |
| `.bot-lock` error | Hapus file `.bot-lock` lalu start ulang |
| `Cloud sync failed` | Cek koneksi internet & Supabase/MongoDB credentials |
| QRIS payment gagal | Cek `SAWERIA_USERNAME` di `.env` |
| WA pairing "couldn't link" | Pastikan nomor WA belum terdaftar di WhatsApp Business |
| Bot tidak respon | Cek token BotFather, restart bot |
| Email tidak terkirim | Ganti `EMAIL_PASS` dengan App Password baru |

### 📞 Kontak Support

Jika ada kendala: [@dikaacode](https://t.me/dikaacode)

---

<p align="center">
  <strong>WhatsApp Recovery Bot</strong> — © 2024-2026 DikaCode
</p>
