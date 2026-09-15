# NewLiveSmp HTTPS Shell (iframe)

HTML terpisah → deploy di hosting **HTTPS gratis** (Cloudflare Pages / Netlify / GitHub Pages).

Backend memakai **localtunnel** custom subdomain:

```
https://shop-newlivesmp.loca.lt
```

## Deploy
1. Upload isi folder ini ke Cloudflare Pages / Netlify (project baru, free).
2. Domain custom opsional: `shops.newlivesmp.fun` → attach di CF Pages.
3. Pastikan RankBot sudah running + tunnel enabled (lihat log `[tunnel] localtunnel OK → https://shop-newlivesmp.loca.lt`).
4. Buka tunnel URL sekali di browser dan bypass halaman IP localtunnel.

## Fitur
- Path browser `/id`, `/shop/id` → iframe load path yang sama di backend
- Title otomatis
- Maintenance UI jika `/health` gagal (pesan: "Server sedang offline atau maintenance…")
- Origin backend mengarah ke tunnel HTTPS

## Ganti ORIGIN
Edit `index.html`, cari `var ORIGIN = …` dan sesuaikan jika subdomain localtunnel berubah (lihat log bot).

## Keamanan
API secret **jangan** ditaruh di HTML ini.
Proteksi API ada di server bot (rate limit, JWT, optional signature).
