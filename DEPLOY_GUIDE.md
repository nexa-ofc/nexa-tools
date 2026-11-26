# Panduan Deploy NEXA-TOOLS

## Cara 1 — GitHub Pages (Gratis, Otomatis) ⭐ Recommended

### Langkah-langkah:

**1. Buat repository GitHub**
- Buka [github.com](https://github.com) → New Repository
- Nama repo bebas, misal: `nexa-tools`
- Set ke **Public** (wajib untuk Pages gratis)
- Jangan centang "Add README" (nanti bentrok)

**2. Upload file ke GitHub**

Cara A — via GitHub website:
- Klik "uploading an existing file"  
- Drag & drop SEMUA file dari folder ini
- Klik "Commit changes"

Cara B — via terminal:
```bash
cd /path/ke/folder/nexa-deploy
git init
git add .
git commit -m "deploy nexa-tools v5.1"
git branch -M main
git remote add origin https://github.com/USERNAME/nexa-tools.git
git push -u origin main
```

**3. Aktifkan GitHub Pages**
- Buka repo → Settings → Pages
- Source: pilih **GitHub Actions**
- Simpan

**4. Tunggu deploy**
- Buka tab Actions — lihat workflow berjalan
- Selesai dalam ~1-2 menit
- URL: `https://USERNAME.github.io/nexa-tools`

---

## Cara 2 — Netlify Drop (Paling Cepat, < 1 menit)

1. Buka [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag & drop **seluruh folder** `nexa-deploy` ke halaman tersebut
3. Selesai — dapat URL langsung seperti `https://random-name.netlify.app`
4. Bisa ganti domain di Netlify dashboard

---

## Cara 3 — Vercel

```bash
npm i -g vercel
cd nexa-deploy
vercel --prod
```

Atau connect GitHub repo di [vercel.com](https://vercel.com) → Import Project.

---

## Cara 4 — Cloudflare Pages

1. Buka [pages.cloudflare.com](https://pages.cloudflare.com)
2. Create a project → Upload assets
3. Upload seluruh isi folder ini
4. Deploy

---

## Cara 5 — VPS / Hosting Biasa

Upload `index.html` ke public_html atau www folder.  
Semua konfigurasi sudah di dalam satu file — tidak butuh apapun lagi.

Nginx config minimal:
```nginx
server {
    listen 80;
    server_name yourdomain.com;
    root /var/www/nexa-tools;
    index index.html;
    location / { try_files $uri $uri/ /index.html; }
}
```

---

## Setelah Deploy

### Login pertama:
```
Username : nexa suka boci
Password : nexa-oficial
```

### Yang perlu dilakukan:
1. Login sebagai Developer
2. Buat akun baru untuk diri sendiri dengan nama yang kamu inginkan
3. Kelola pengguna → hapus atau edit akun default jika perlu
4. Generate kode redeem untuk pengguna yang perlu upgrade role

### Catatan penting:
- Semua data tersimpan di **localStorage browser** pengguna masing-masing
- Data tidak sinkron antar device (by design — private tool)
- Password tersimpan dalam format btoa (base64) — cukup untuk tool private
- Untuk keamanan lebih tinggi, deploy di HTTPS (semua cara di atas sudah HTTPS)

