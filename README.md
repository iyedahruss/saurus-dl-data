# saurus-dl-data

Repo privat ini HANYA menyimpan data (JSON metadata script & kategori) dan
file ZIP hasil upload. Jangan hubungkan repo ini ke Vercel sebagai deployment —
repo ini murni dipakai sebagai "database" via GitHub Contents API oleh backend
di repo kode utama (`saurus-dl`).

## Struktur folder
- `data/scripts/*.json` — metadata tiap script (1 file per slug)
- `data/categories/*.json` — metadata tiap kategori (1 file per slug)
- `uploads/*.zip` — file ZIP script yang diupload dari admin dashboard

## Cara pakai
1. Buat Personal Access Token GitHub (scope: `repo`) khusus untuk mengakses repo ini.
2. Di project Vercel repo kode utama, set environment variables:
   - `DATA_GITHUB_TOKEN` = token di atas
   - `DATA_GITHUB_OWNER` = username/organisasi pemilik repo ini
   - `DATA_GITHUB_REPO` = saurus-dl-data
3. Push folder `data/` dan `uploads/` di repo ini (isi awal sudah disediakan
   sebagai migrasi dari data lama).
4. Set repo ini ke **Private**.
