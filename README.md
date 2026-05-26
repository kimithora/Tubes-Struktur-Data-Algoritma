# Tubes STD & Algo

## Deskripsi
Proyek ini berisi notebook Python untuk mengunduh dataset churn dari Kaggle, memuat file CSV, dan menampilkan informasi dasar menggunakan `pandas`.

## File Projek
- `cek data.ipynb` - Notebook utama yang mengunduh data dari dataset Kaggle `shrutimechlearn/churn-modelling`, lalu membaca dan menampilkan ringkasan `Churn_Modelling.csv`.
- `README.md` - Dokumentasi proyek ini.

## Cara Menjalankan
1. Pastikan Python sudah terpasang di komputer.
2. Install library yang diperlukan:
   - `pip install kagglehub pandas numpy`
3. Buka `cek data.ipynb` di Jupyter Notebook / Jupyter Lab / VS Code.
4. Jalankan sel kode secara berurutan.

## Library yang Dibutuhkan
- `kagglehub`
- `pandas`
- `numpy`

## Catatan
- Notebook ini menggunakan `kagglehub.dataset_download` untuk mengunduh dataset dari Kaggle.
- Pastikan Anda memiliki akses atau kredensial Kaggle yang valid jika diperlukan oleh `kagglehub`.

## Tujuan
Notebook ini digunakan untuk:
- Mengunduh dataset churn dari Kaggle
- Memuat data ke dalam `pandas.DataFrame`
- Menampilkan informasi struktur dataset menggunakan `df.info()`
