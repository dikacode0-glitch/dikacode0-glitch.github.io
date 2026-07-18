<div align="center">
  <img src="https://files.catbox.moe/ecvmlf.jpg" alt="Logo" width="120" height="120" style="border-radius: 20px;" />

  <h1 align="center">🤖 WhatsApp Recovery Bot</h1>

  <p align="center">
    <strong>Telegram Bot untuk Recovery &amp; Verifikasi Akun WhatsApp</strong>
    <br />
    Kirim appeal massal, fix code OTP, cek nomor WA, dan kelola akun — langsung dari Telegram!
    <br />
    <br />
    <a href="#-features">📋 Features</a>
    ·
    <a href="#-setup">⚙️ Setup</a>
    ·
    <a href="#-usage">🚀 Usage</a>
    ·
    <a href="#-admin-panel">🛡️ Admin</a>
    ·
    <a href="#-tech-stack">🧱 Tech Stack</a>
    <br />
    <br />
    <a href="https://t.me/dikaacode">
      <img src="https://img.shields.io/badge/BUY-Rp50.000-FF5733?logo=telegram&amp;logoColor=white&amp;style=for-the-badge" alt="Buy Rp50.000" />
    </a>
    <a href="https://t.me/dikaacode">
      <img src="https://img.shields.io/badge/Contact-@dikaacode-0088CC?logo=telegram&amp;logoColor=white&amp;style=for-the-badge" alt="Contact @dikaacode" />
    </a>
  </p>

  <p align="center">
    <img src="https://img.shields.io/badge/Node.js-18%2B-339933?logo=node.js&amp;logoColor=white" />
    <img src="https://img.shields.io/badge/WhatsApp-Baileys-25D366?logo=whatsapp&amp;logoColor=white" />
    <img src="https://img.shields.io/badge/Telegram-Bot_API-2CA5E0?logo=telegram&amp;logoColor=white" />
    <img src="https://img.shields.io/badge/Email-SMTP-EA4335?logo=gmail&amp;logoColor=white" />
    <img src="https://img.shields.io/badge/Payment-QRIS-FF5722?logo=react&amp;logoColor=white" />
    <img src="https://img.shields.io/badge/Database-Supabase-3ECF8E?logo=supabase&amp;logoColor=white" />
    <img src="https://img.shields.io/badge/Database-MongoDB-47A248?logo=mongodb&amp;logoColor=white" />
  </p>
</div>

---

## 📋 Table of Contents

- [✨ Features](#-features)
- [⚙️ Setup](#️-setup)
- [🚀 Usage](#-usage)
- [🎁 Referral Program](#-referral-program)
- [👑 VIP Premium](#-vip-premium)
- [🛡️ Admin Panel](#️-admin-panel)
- [📁 Project Structure](#-project-structure)
- [🧱 Tech Stack](#-tech-stack)
- [☁️ Cloud Backup (Supabase + MongoDB)](#️-cloud-backup-supabase--mongodb)
- [🔒 Security](#-security)
- [📄 License](#-license)

---

## ✨ Features

### 📧 Email Services
| Fitur | Deskripsi |
|-------|-----------|
| **Fix Login Unavailable** | Kirim email appeal ke 60+ alamat support WhatsApp untuk error &quot;Login Unavailable&quot; |
| **Fix Code 1 Jam** | Atasi error &quot;Try Again in 1 Hour&quot; — kirim laporan OTP tidak terkirim |
| **Request SMS Code** | Minta WhatsApp kirimkan SMS OTP (bukan Call) untuk verifikasi |

Setiap email dikirim dengan **staggered delivery** (delay acak antar email), **CC rotation**, dan **template bervariasi** (5+ template berbeda) agar terlihat natural &amp; tidak terdeteksi spam.

### 📱 WhatsApp Checker
| Fitur | Deskripsi |
|-------|-----------|
| **Pair Device** | Hubungkan nomor WhatsApp via **Pairing Code** (bukan QR) |
| **Cek Nomor** | Periksa apakah nomor terdaftar di WhatsApp + lihat Bio |
| **Batch Check** | Upload file `.txt` — periksa ratusan nomor sekaligus |

Auto-reconnect saat 515/restartRequired — pairing tetap berhasil sampai device benar-benar ter-link.

### 🎁 Referral Program
- Dapatkan **token gratis** dengan mengajak teman
- 1 referral = +1 Appeal, +1 FixCode, +1 SMS token
- Token = akses instan tanpa cooldown
- **Share Link** — bagikan referral langsung ke chat Telegram

### 👑 VIP Premium
- ✅ Akses unlimited — kirim appeal &amp; fixcode tanpa batas
- ✅ Tanpa cooldown &amp; tanpa token
- ✅ Pembayaran via **QRIS**
- ✅ Custom durasi (1–365 hari)
- Harga: **Rp1.000/hari**

### 💝 Donasi Email
User bisa **donasikan akun Gmail** mereka untuk jadi server pengirim tambahan. Email diverifikasi otomatis (SMTP check) sebelum ditambahkan.

### 🔐 Channel Verification
User wajib join channel Telegram tertentu sebelum bisa menggunakan bot. Verifikasi otomatis melalui tombol **VERIFY**.

---

## 💰 Pricing

| Item | Harga |
|------|-------|
| **Script Full** | **Rp50.000** |

**Free update** — setelah beli, dapat update selamanya gratis.

**Contact:** [@DikaCode](https://t.me/DikaCode)

---

## 🚀 Quick Start

Jalankan Bot:

```bash
npm install     # Install dependencies
npm start       # Start bot
```

> 💡 Lihat [HOWTOINSTALL.md](HOWTOINSTALL.md) untuk panduan instalasi lengkap.

---

## ⚙️ Requirements

- **Node.js** 18+ (LTS recommended)
- **Telegram Bot Token** (dari [@BotFather](https://t.me/BotFather))
- **Gmail App Password** untuk server email primer

---

## 🚀 Usage

### User Commands

| Command | Deskripsi |
|---------|-----------|
| `/start` | Menu utama &amp; registrasi |
| `/start ref_&lt;id&gt;` | Join via referral link (otomatis) |
| `/vip` | Info &amp; pembelian VIP premium |

### Tombol Menu

```
📧 FIX LOGIN UNAVAILABLE
    → Masukkan nomor HP (62xx)
    → Pilih server email
    → Email appeal terkirim ke 60+ alamat support WA

⏱ FIX CODE 1 JAM
    → Masukkan nomor HP (62xx)
    → Pilih server email
    → Laporan OTP error terkirim

📨 FIX NO OPSI SMS
    → Masukkan nomor HP (62xx)
    → Minta WhatsApp kirim SMS code

📱 BIO WA CHECKER
    → Pair device → Cek nomor / Upload .txt
```

### Flow Appeal
```
User klik "📧 FIX LOGIN UNAVAILABLE"
    ↓
Cek membership channel (wajib join)
    ↓
Cek cooldown / referral token
    ↓
Masukkan nomor HP (628xx)
    ↓
Pilih server email (server 1, 2, atau custom)
    ↓
✅ Email terkirim ke support WhatsApp
    ↓
Cooldown 1 jam (free user) / token dipakai
```

---

## 🎁 Referral Program

Dapatkan **token gratis** dengan mengajak teman menggunakan link referral unikmu.

```
🎁 PROGRAM REFERRAL

📊 Saldo Token:
  📧 Appeal: 2 token
  ⏱ FixCode: 2 token
  📨 SMS: 0 token

🔗 Link Kamu:
https://t.me/yourbot?start=ref_123456

💡 Cara kerja:
  1. Bagikan link ke teman
  2. Teman klik link & JOIN semua channel
  3. Teman tekan VERIFY
  4. Kamu dapat +1 Appeal, FixCode & SMS
```

**Token** digunakan untuk akses instan tanpa cooldown. Cocok untuk user free yang ingin kirim ulang tanpa menunggu.

---

## 👑 VIP Premium

Akses unlimited ke semua fitur dengan pembayaran QRIS.

| Durasi | Harga | Pembayaran |
|--------|-------|------------|
| 1 hari | Rp1.000 | ✅ QRIS |
| 2 hari | Rp2.000 | ✅ QRIS |
| 3 hari | Rp3.000 | ✅ QRIS |
| 7 hari | Rp7.000 | ✅ QRIS |
| 30 hari | Rp30.000 | ✅ QRIS |
| Custom | Rp1.000/hari | ✅ QRIS |

Pembayaran diproses otomatis — setelah lunas, VIP langsung aktif. Polling status 5 detik dengan countdown.

---

## 🛡️ Admin Panel

Akses: `⚙️ ADMIN` (khusus owner/developer)

| Menu | Fungsi |
|------|--------|
| **👑 ADD PREMIUM** | Beri akses premium ke user |
| **👑 REM PREMIUM** | Cabut akses premium |
| **📋 LIST PREMIUM** | Lihat semua user premium |
| **👥 ALL USERS** | Statistik &amp; daftar user |
| **📢 BROADCAST** | Kirim pesan ke semua user |
| **💝 ADD EMAIL** | Tambah server email donasi |
| **📋 LIST EMAIL** | Lihat server email aktif |
| **🗑 DELETE EMAIL** | Hapus server email |
| **📱 LIST DEVICE** | Lihat device WA terpair |
| **🗑 HAPUS DEVICE** | Hapus device WA |
| **👑 ADD/REMOVE OWNER** | Kelola owner (dev-only) |

Admin panel menampilkan dashboard:
```
╔ ⭐ Developer
║ 👥 Users: 150
║ 👑 Premium: 5 (3 permanen, 2 terbatas)
║ 📱 Devices: 2/3 online
╚ 💝 Donasi: 8 server
```

---

## 📁 Project Structure

```
📦 whatsapp-appeal-bot/
├── 📄 index.js                 # Entry point + graceful shutdown
├── 📄 .env                     # Environment variables
├── 📄 .env.example             # Template env
├── 📄 package.json             # Dependencies
├── 📄 supabase-migration.sql   # SQL untuk Supabase tables
│
├── 📁 src/                     # Bot source code
│   ├── 📄 bot.js               # Telegram bot handlers (main logic)
│   ├── 📄 ui.js                # UI helpers — keyboard builder, sendMessage, etc.
│   ├── 📄 config.js            # Config — env vars, templates, email lists
│   ├── 📄 email-templates.js   # Email body/subject templates
│   ├── 📄 db.js                # Database layer — JSON file store accessors
│   ├── 📄 store.js             # JSON file store class (atomic saves)
│   ├── 📄 state.js             # User state machine + rate limiter + cooldown
│   ├── 📄 email.js             # Email delivery — sendAppeal, sendFixCode, sendSmsRequest
│   ├── 📄 wa.js                # WhatsApp Multi-Device — pair, QR, check numbers
│   ├── 📄 inbox.js             # Inbox polling — baca balasan email dari support
│   ├── 📄 saweria.js           # Saweria QRIS payment integration
│   ├── 📄 qris-img.js          # QRIS image generator
│   ├── 📄 proxy-rotator.js     # SOCKS5 proxy rotator
│   ├── 📄 cloud-db.js          # Supabase cloud backup (fire-and-forget)
│   └── 📄 mongo-db.js          # MongoDB cloud backup (fire-and-forget)
│
├── 📁 sessions/                # WhatsApp session data (auto-generated)
├── 📁 data/                    # Sent emails log (auto-generated)
│
├── 📄 users.json               # User database (auto-generated)
├── 📄 premium.json             # Premium members (auto-generated)
├── 📄 owners.json              # Bot owners (auto-generated)
├── 📄 devices.json             # WA devices (auto-generated)
├── 📄 referrals.json           # Referral balances (auto-generated)
├── 📄 donated_servers.json     # Donated email servers (auto-generated)
├── 📄 purchases.json           # Purchase history (auto-generated)
└── 📄 rate-limit-state.json    # Rate limit persistence (auto-generated)
```

---

## 🧱 Tech Stack

| Technology | Purpose |
|-----------|---------|
| **Node.js** | Runtime |
| **node-telegram-bot-api** | Telegram Bot API wrapper |
| **@whiskeysockets/baileys** | WhatsApp Multi-Device client |
| **nodemailer** | Email delivery via Gmail SMTP |
| **@supabase/supabase-js** | Cloud backup (PostgreSQL) |
| **mongodb** | Cloud backup (MongoDB Atlas) |
| **pino + pino-pretty** | Logging |

### API Integration

- **Telegram Bot API** — semua request via `fetch()` langsung (tanpa library abstraksi) untuk dukungan penuh inline keyboard style
- **WhatsApp Web API** — Baileys MD (Multi-Device) protocol
- **Gmail SMTP** — email delivery dengan staggered delay anti-spam
- **Supabase REST API** — cloud backup via service_role key
- **MongoDB Atlas** — cloud backup NoSQL (redundancy) via native driver

---

## ☁️ Cloud Backup (Supabase + MongoDB)

Bot otomatis mem-backup semua data ke **dua cloud database sekaligus** setiap kali ada perubahan:

1. **Supabase (PostgreSQL)** — tabel relasional
2. **MongoDB Atlas** — dokumen NoSQL

Redundansi penuh — jika satu cloud down, data tetap aman di cloud lain + file JSON lokal.

### Fitur
- ✅ Fire-and-forget — tidak blokir response bot
- ✅ Setiap `save()` lokal → langsung sync ke kedua cloud secara paralel
- ✅ Full sync saat startup + periodic tiap 5 menit
- ✅ Non-blocking — bot tetap jalan walau salah satu atau kedua cloud error
- ✅ Encrypted password untuk email server

### Supabase Tables

| Table | Primary Key | Isi |
|-------|-------------|-----|
| `users` | `id` (BIGINT) | Data user Telegram |
| `owners` | `id` (BIGINT) | Bot admin |
| `premium` | `id` (BIGINT) | VIP members |
| `referrals` | `user_id` (BIGINT) | Token balances |
| `devices` | `chat_id` (BIGINT) | WA sessions |
| `donated_servers` | `id` (TEXT) | Email servers (encrypted) |

### MongoDB Collections

Sama persis struktur dengan tabel Supabase di atas.

### Setup Cloud Backup

#### Supabase
1. Daftar di [supabase.com](https://supabase.com) (Free tier 500MB)
2. Buat project, buka **SQL Editor**, paste & jalankan `supabase-migration.sql`
3. Isi `.env`:
```env
SUPABASE_URL=https://your-project.supabase.co
SUPABASE_SERVICE_KEY=your_service_role_key
```

#### MongoDB
1. Daftar di [mongodb.com/atlas](https://mongodb.com/atlas) (Free tier 512MB)
2. Buat cluster, buat database user, allow IP 0.0.0.0/0 (atau IP VPS kamu)
3. Dapatkan connection string, isi `.env`:
```env
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/?appName=YourApp
```

---

## 🔒 Security

- **App Passwords** — tidak pernah menyimpan password Gmail asli, hanya App Password 16 karakter
- **Encryption** — password email server di-enkripsi (AES-256-CBC) sebelum disimpan
- **Channel Gate** — user wajib join channel sebelum akses bot
- **Rate Limiting** — sliding window (3 request/menit) + cooldown 1 jam (free user)
- **Privacy** — nomor HP &amp; email user dihapus dari chat setelah diproses

---

## ❓ Troubleshooting

| Problem | Solution |
|---------|----------|
| Bot tidak merespon | Pastikan `BOT_TOKEN` benar, restart bot |
| Pairing WA gagal | Coba ulang, pastikan nomor benar (62xx) |
| Email tidak terkirim | Cek App Password, coba custom email |
| Supabase sync error | Cek `SUPABASE_URL` &amp; `SUPABASE_SERVICE_KEY` |
| &quot;Login Unavailable&quot; | Itu yang mau di-fix — kirim appeal! |

---

## 📄 License

Distributed under the MIT License.

---

<div align="center">
  <p>Made with ❤️ for the WhatsApp recovery community</p>
  <p>
    <a href="https://t.me/execuidorbaru">📢 Channel</a>
    ·
    <a href="https://t.me/dikaacode">🐛 Report Bug</a>
    ·
    <a href="https://t.me/dikaacode">✨ Request Feature</a>
  </p>
</div>
