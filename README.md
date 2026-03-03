# 🎨 Coret-Coret — Frontend (Cloudflare Pages)

## Deploy ke Cloudflare Pages

### Langkah 1 — Upload ke GitHub
1. Buat repo baru di GitHub (misal: `coret-coret-frontend`)
2. Upload file `index.html` ini ke repo tersebut

### Langkah 2 — Connect ke Cloudflare Pages
1. Buka [Cloudflare Dashboard](https://dash.cloudflare.com)
2. Pilih **Workers & Pages** → **Create application** → **Pages**
3. Connect ke GitHub repo `coret-coret-frontend`
4. Build settings:
   - **Framework preset**: None
   - **Build command**: *(kosongkan)*
   - **Build output directory**: `/` atau `.`
5. Klik **Save and Deploy**

### Langkah 3 — Atur URL Backend
Setelah backend berhasil di-deploy (lihat README backend), edit `index.html`:

```javascript
// Baris ini ada di bagian atas script
const BACKEND_URL = 'GANTI_DENGAN_URL_WORKER_KAMU';

// Ganti dengan URL Worker kamu, contoh:
const BACKEND_URL = 'https://coret-coret-backend.namakamu.workers.dev';
```

Lalu push ulang ke GitHub → Cloudflare Pages akan auto-redeploy.

---

## Urutan Deploy yang Benar

1. ✅ Deploy **backend** dulu → dapat URL Worker
2. ✅ Isi `BACKEND_URL` di `index.html` dengan URL Worker
3. ✅ Push frontend ke GitHub
4. ✅ Deploy di Cloudflare Pages
