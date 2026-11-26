# NEXA-TOOLS v5.1

Dashboard tools premium berbasis web — single-file HTML, zero dependencies, siap deploy.

## Fitur
- Splash sidik jari (tahan sensor 2.2 detik)
- Sistem login multi-role (Developer / Owner / Free)
- Dashboard Home: cuaca real-time, berita terkini, info developer
- Dashboard Tools: generate premium AM dengan 2 tahap verifikasi
- Paket FREE (GPA Android, 10x/minggu) & ULTRA (Apple 10 karakter, unlimited)
- Dynamic Island musik — search iTunes, play preview
- Kode Redeem: Developer generate → user input → role up otomatis
- Kelola pengguna: lihat masa aktif, hapus (logout paksa)
- Full-screen modals, neobrutalism design, mobile-first

## Deploy

### GitHub Pages (otomatis via Actions)
1. Fork/clone repo ini
2. Push ke branch `main`
3. GitHub Actions akan deploy ke `gh-pages` otomatis
4. Aktifkan Pages di Settings → Pages → Source: `gh-pages`

### Netlify Drop
Drag folder ini ke [netlify.com/drop](https://app.netlify.com/drop)

### Vercel
```bash
npx vercel --prod
```

### Manual / VPS
Upload `index.html` ke web server apapun (nginx, apache, caddy).  
Tidak butuh backend — semua state di localStorage browser pengguna.

## Kredensial Default
```
Username : nexa suka boci
Password : nexa-oficial
Role     : Developer
```
Ganti via "Kelola Pengguna" setelah login pertama.

## Stack
- Vanilla HTML/CSS/JS (zero framework, zero build step)
- Fonts: Google Fonts (Creepster, Rubik, Share Tech Mono)
- API: Open-Meteo (cuaca), RSS2JSON (berita), iTunes Search (musik)
- Storage: localStorage (semua data di device pengguna)

## Lisensi
Private — © 2024 Xzar / NEXA-TOOLS
