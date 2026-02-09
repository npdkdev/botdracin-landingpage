# 🌐 Custom Domain Setup - IDWebhost ke Cloudflare Pages

Panduan lengkap menghubungkan domain dari IDWebhost ke Cloudflare Pages.

---

## 📋 Overview

Ada 2 metode setup:

1. **Method A: Full Cloudflare (Recommended)** - Transfer nameservers ke Cloudflare
2. **Method B: DNS Only** - Tetap pakai nameserver IDWebhost, tambah DNS record saja

---

## 🏆 Method A: Full Cloudflare (RECOMMENDED)

**Keuntungan:**
- ✅ SSL/HTTPS otomatis
- ✅ DDoS protection gratis
- ✅ Analytics & Web Vitals
- ✅ Cache optimization
- ✅ Setup lebih mudah
- ✅ Performance maksimal

### Step 1: Tambah Domain ke Cloudflare

1. **Login Cloudflare Dashboard**: https://dash.cloudflare.com/
2. Klik **"Add a Site"** (pojok kanan atas)
3. **Masukkan domain Anda** (contoh: `vipbot.com`)
4. **Pilih plan**: FREE (sudah cukup)
5. Klik **"Continue"**

### Step 2: Cloudflare Scan DNS Records

1. Cloudflare akan otomatis scan DNS records dari IDWebhost
2. **Review records** yang ditemukan
3. Pastikan record penting ada (A, MX, CNAME, dll)
4. Klik **"Continue"**

### Step 3: Dapatkan Cloudflare Nameservers

Cloudflare akan memberikan 2 nameserver, contoh:
```
abby.ns.cloudflare.com
zeke.ns.cloudflare.com
```

**⚠️ CATAT nameserver ini!**

### Step 4: Update Nameserver di IDWebhost

1. **Login ke IDWebhost**: https://clientarea.idwebhost.com/
2. Pilih **"Domain"** → **"Domain Saya"**
3. Klik domain yang mau diubah
4. Pilih **"Nameservers"** atau **"DNS Management"**
5. **Ubah dari "IDWebhost Nameservers" ke "Custom Nameservers"**
6. **Masukkan nameserver Cloudflare**:
   ```
   Nameserver 1: abby.ns.cloudflare.com
   Nameserver 2: zeke.ns.cloudflare.com
   ```
7. **Save Changes**

⏱️ **Propagation time**: 5 menit - 48 jam (biasanya 1-4 jam)

### Step 5: Verifikasi di Cloudflare

1. Kembali ke **Cloudflare Dashboard**
2. Klik **"Done, check nameservers"**
3. Tunggu verifikasi (Cloudflare akan cek otomatis setiap 5 menit)
4. Setelah verified, status berubah jadi **"Active"**

### Step 6: Connect Domain ke Cloudflare Pages

1. Di Cloudflare Dashboard, pilih domain Anda
2. Menu **"Workers & Pages"**
3. Klik project **"botdracin-landingpage"**
4. Tab **"Custom domains"**
5. Klik **"Set up a custom domain"**
6. **Masukkan domain** (contoh: `vipbot.com` atau `www.vipbot.com`)
7. Klik **"Continue"**

Cloudflare akan otomatis:
- ✅ Create DNS record (CNAME)
- ✅ Generate SSL certificate
- ✅ Setup redirect (www ↔ non-www)

### Step 7: Test Domain

Tunggu 5-10 menit, lalu buka domain Anda:
```
https://vipbot.com
https://www.vipbot.com
```

**Done!** 🎉

---

## 🔧 Method B: DNS Only (Tanpa Transfer Nameserver)

**Jika tidak mau pindah nameserver:**

### Step 1: Get CNAME Target

1. **Cloudflare Dashboard** → **Workers & Pages**
2. Klik project **"botdracin-landingpage"**
3. Tab **"Custom domains"**
4. Klik **"Set up a custom domain"**
5. Masukkan domain (contoh: `www.vipbot.com`)
6. Cloudflare akan tampilkan **CNAME record** yang harus dibuat

Contoh:
```
Type: CNAME
Name: www
Target: botdracin-landingpage.pages.dev
```

### Step 2: Tambah CNAME di IDWebhost

1. **Login IDWebhost**: https://clientarea.idwebhost.com/
2. **Domain** → **Domain Saya** → Pilih domain
3. **DNS Management** atau **Zone Editor**
4. **Add Record** / **Tambah Record**
5. Isi form:
   ```
   Type: CNAME
   Host/Name: www
   Points to/Value: botdracin-landingpage.pages.dev
   TTL: 3600 (atau Auto)
   ```
6. **Save**

### Step 3: Setup SSL (Manual)

⚠️ **Problem**: Dengan DNS only, Cloudflare tidak bisa auto-generate SSL.

**Solusi**:

**Option 1**: Pakai SSL dari IDWebhost (jika tersedia)

**Option 2**: Gunakan subdomain saja (`www.vipbot.com`) dan setup SSL via Let's Encrypt di IDWebhost

**Option 3**: Pindah ke Method A (lebih mudah)

---

## 🎯 Rekomendasi Setup

### Untuk Root Domain (vipbot.com)

**Setup keduanya:**

1. **Root domain** (`vipbot.com`):
   ```
   Type: A
   Name: @
   Value: 192.0.2.1 (Cloudflare proxy placeholder)
   Proxy: ON (orange cloud)
   ```

2. **WWW subdomain** (`www.vipbot.com`):
   ```
   Type: CNAME
   Name: www
   Target: botdracin-landingpage.pages.dev
   Proxy: ON (orange cloud)
   ```

3. **Redirect**: Setup redirect `vipbot.com` → `www.vipbot.com` (atau sebaliknya)

---

## ⚠️ Troubleshooting

### DNS belum propagate?

Check status:
```bash
# Terminal
nslookup vipbot.com
dig vipbot.com

# Online tools
https://dnschecker.org/
https://www.whatsmydns.net/
```

### SSL Error / Not Secure?

- Tunggu 10-15 menit untuk SSL provisioning
- Pastikan Cloudflare Proxy (orange cloud) ON
- Cek di Cloudflare: **SSL/TLS** → set mode **"Full"** atau **"Full (strict)"**

### Domain tidak mengarah ke Pages?

1. Cek DNS record sudah benar
2. Pastikan CNAME target: `botdracin-landingpage.pages.dev`
3. Clear browser cache (Ctrl+Shift+R)
4. Tunggu DNS propagation (max 48 jam)

### IDWebhost Error?

- Beberapa shared hosting IDWebhost lock nameserver changes
- Contact IDWebhost support jika tidak bisa ubah nameserver
- Alternative: Pakai Method B (DNS only)

---

## 📞 IDWebhost Support

Jika ada kendala:
- **Website**: https://idwebhost.com/
- **Support**: https://idwebhost.com/kontak-kami
- **Live Chat**: Available di dashboard
- **Email**: support@idwebhost.com
- **WhatsApp**: 0821-3333-4000

---

## ✅ Checklist Setup

- [ ] Domain sudah aktif di IDWebhost
- [ ] Domain tidak terkunci (unlock domain)
- [ ] Cloudflare account sudah dibuat
- [ ] Nameserver Cloudflare sudah dicatat
- [ ] Nameserver di IDWebhost sudah diupdate
- [ ] DNS propagation selesai (cek dnschecker.org)
- [ ] Domain verified di Cloudflare
- [ ] Custom domain connected di Cloudflare Pages
- [ ] SSL certificate aktif (HTTPS)
- [ ] Test domain sudah bisa diakses

---

## 🎬 Video Tutorial (Jika Butuh)

Berikut keyword untuk cari tutorial video:
- "cara pindah nameserver idwebhost ke cloudflare"
- "setup cloudflare pages custom domain"
- "cloudflare nameserver tutorial indonesia"

---

## 💡 Tips Pro

1. **Gunakan Method A** - Transfer nameserver untuk pengalaman terbaik
2. **Setup www + non-www** - Agar kedua versi berfungsi
3. **Enable HSTS** - Extra security di Cloudflare SSL/TLS settings
4. **Setup Analytics** - Enable Cloudflare Web Analytics gratis
5. **Email forwarding** - Jangan lupa setup MX records jika punya email @domain.com

---

**Butuh bantuan setup? Tanya saya jika ada kendala!** 🚀
