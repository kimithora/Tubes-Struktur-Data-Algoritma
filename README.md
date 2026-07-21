# Proyek Analisis Data Churn

## Deskripsi Singkat
Repositori ini berisi kerjaan tugas akhir / praktikum yang berfokus pada analisis data customer churn dan implementasi algoritma statistik.

File-file utama dalam projek:
- `Churn_Modelling.csv` : dataset utama yang digunakan untuk eksplorasi dan pemodelan.
- `EDAAlgo.ipynb` : notebook untuk eksplorasi data dan analisis algoritma.
- `EDAstd.IPYNB` : notebook untuk analisis statistik dan eksplorasi fitur.
- `trialerror.ipynb` : notebook percobaan dan eksperimen tambahan.
- `cek data.ipynb` : notebook untuk pemeriksaan awal data.
- `README.md` : panduan penggunaan proyek ini.
- `PROJECT_OVERVIEW.md` : ringkasan struktur dan cara memahami isi repositori.

## Cara Menggunakan
1. Buka proyek ini di VS Code.
2. Aktifkan environment Python virtual jika tersedia:
   ```powershell
   .\.venv\Scripts\Activate.ps1
   ```
3. Jika dependensi belum terpasang, pasang paket Python yang diperlukan:
   ```powershell
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```
4. Jalankan Jupyter Notebook untuk melihat dan menjalankan analisis:
   ```powershell
   jupyter notebook
   ```
5. Buka notebook yang ingin Anda pelajari atau modifikasi.

## Struktur Notebook
- `cek data.ipynb` : pemeriksaan awal data dan validasi format.
- `EDAstd.IPYNB` : eksplorasi data statistik dasar, distribusi, dan ringkasan fitur.
- `EDAAlgo.ipynb` : eksplorasi data lanjutan dan aplikasi algoritma pada dataset.
- `trialerror.ipynb` : eksperimen tambahan, percobaan pendekatan baru, dan catatan pengujian.

## Menjalankan Analisis
- Notebook dirancang untuk dijalankan sel baris per baris.
- Pastikan `Churn_Modelling.csv` berada di folder yang sama dengan notebook.
- Ubah path file dalam sel jika diperlukan untuk mencocokkan struktur folder Anda.

## Catatan
- `README.md` ini hanya berisi panduan penggunaan dan struktur umum.
- Jangan menghapus `Churn_Modelling.csv` atau notebook jika Anda ingin melanjutkan eksperimen.
- `PROJECT_OVERVIEW.md` berisi petunjuk tambahan dan penjelasan file tanpa detail hasil analisis.

## Tips
- Gunakan `Ctrl+Shift+P` lalu pilih `Python: Select Interpreter` untuk memastikan environment `.venv` aktif.
- Jika notebook gagal dijalankan karena paket tidak ditemukan, pasang paket yang diperlukan.
- Simpan perubahan notebook secara teratur.
