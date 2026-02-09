# 🚀 Deploy ke Cloudflare Pages

Repository sudah berhasil dibuat dan di-push ke GitHub:
**https://github.com/npdkdev/botdracin-landingpage**

---

## 📋 Langkah Deploy ke Cloudflare Pages

### 1️⃣ Login ke Cloudflare Dashboard
1. Buka: **https://dash.cloudflare.com/**
2. Login dengan akun Cloudflare Anda
3. Jika belum punya akun, daftar gratis di **https://cloudflare.com/**

---

### 2️⃣ Buat Project Cloudflare Pages

1. **Dari dashboard**, klik **"Workers & Pages"** di sidebar kiri
2. Klik tombol **"Create application"**
3. Pilih tab **"Pages"**
4. Klik **"Connect to Git"**

---

### 3️⃣ Connect ke GitHub Repository

1. Klik **"Connect GitHub"**
2. Authorize Cloudflare untuk akses GitHub Anda
3. Pilih repository: **`npdkdev/botdracin-landingpage`**
4. Klik **"Begin setup"**

---

### 4️⃣ Configure Build Settings

Isi form dengan setting berikut:

```
Project name: botdracin-landingpage
Production branch: main

Build settings:
├─ Framework preset: Vite
├─ Build command: npm run build
├─ Build output directory: dist
└─ Root directory: (leave empty)

Environment variables:
└─ VITE_GEMINI_API_KEY = (masukkan API key Gemini Anda)
```

**⚠️ PENTING**: Tambahkan environment variable untuk Gemini API:
- Variable name: `VITE_GEMINI_API_KEY`
- Value: API key Gemini Anda (dari Google AI Studio)
- Klik **"Add variable"**

---

### 5️⃣ Deploy!

1. Klik **"Save and Deploy"**
2. Tunggu build process selesai (~2-3 menit)
3. Setelah selesai, Anda akan mendapat URL: **`https://botdramacina.biz.id`**

---

## 🎯 Setelah Deploy

### ✅ Custom Domain (Opsional)
Jika ingin pakai domain sendiri:
1. Pergi ke tab **"Custom domains"**
2. Klik **"Set up a custom domain"**
3. Masukkan domain Anda (contoh: `vipbot.com`)
4. Follow instruksi untuk setup DNS

### ✅ Auto Deploy
Setiap kali Anda push ke GitHub (branch `main`), Cloudflare Pages otomatis:
- Build ulang
- Deploy versi terbaru
- Update production URL

### ✅ Preview Deployments
Setiap pull request akan dapat URL preview terpisah untuk testing.

---

## 🔧 Deploy Manual via CLI (Alternative)

Jika ingin deploy langsung dari terminal:

```bash
# Install Wrangler CLI (hanya sekali)
npm install -g wrangler

# Login ke Cloudflare
wrangler login

# Build project
npm run build

# Deploy
wrangler pages deploy dist
```

---

## 📊 Monitoring

Setelah deploy, Anda bisa monitor:
- **Analytics**: Traffic, page views, unique visitors
- **Build history**: Semua deployment history
- **Logs**: Real-time deployment logs
- **Performance**: Web Vitals metrics

Access semua ini dari Cloudflare Pages dashboard.

---

## 🆘 Troubleshooting

### Build gagal?
- Cek "View build logs" untuk error details
- Pastikan environment variable `VITE_GEMINI_API_KEY` sudah diset
- Pastikan dependencies di `package.json` lengkap

### Deployment lambat?
- Build pertama biasanya lebih lama (~3-5 menit)
- Build selanjutnya lebih cepat karena caching (~1-2 menit)

---

## 🎉 Done!

Landing page Anda sekarang live di:
- Production: `https://botdramacina.biz.id`
- GitHub Repo: https://github.com/npdkdev/botdracin-landingpage

**Next Steps:**
1. Test semua fitur di production URL
2. Setup custom domain (jika ada)
3. Share link ke client! 🚀
