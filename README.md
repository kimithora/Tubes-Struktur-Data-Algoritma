# Tubes STD & Algo

## Deskripsi
Proyek ini berisi analisis eksplorasi data (EDA) untuk dataset `Churn_Modelling.csv` dari Kaggle. Notebook melakukan:
- unduhan dataset Kaggle
- pembacaan file CSV dengan `pandas`
- pemeriksaan kualitas data
- statistik deskriptif
- visualisasi univariat fitur numerik dan kategorikal

## File Proyek
- `cek data.ipynb` - Notebook awal yang mengunduh dataset dan menampilkan ringkasan dasar.
- `EDA.ipynb` - Notebook EDA utama yang sudah diperbarui dengan pemeriksaan struktur, kualitas data, statistik deskriptif, dan visualisasi distribusi.
- `README.md` - Dokumentasi dan ringkasan pekerjaan.

## Ringkasan Pekerjaan yang Dilakukan
1. Unduh dataset `shrutimechlearn/churn-modelling` dari Kaggle menggunakan `kagglehub`.
2. Baca file `Churn_Modelling.csv` ke dalam DataFrame `df` menggunakan `pandas`.
3. Tampilkan informasi dasar dataset dengan `df.info()` dan `df.head()`.
4. Buat kelas bantu untuk:
   - `DatasetDescription`: menampilkan ukuran dataset, nama kolom, dan preview data.
   - `DataQualityCheck`: memeriksa missing values, duplikat, dan tipe data.
   - `DescriptiveStatistics`: menghitung ringkasan statistik dan skewness kolom numerik.
   - `UnivariateAnalysis`: membuat histogram, boxplot, dan countplot untuk setiap fitur.
5. Jalankan semua pemeriksaan di atas untuk mendapatkan pemahaman awal tentang isi dataset.

## Timeline Perubahan
- **20 Mei 2026**: buat `cek data.ipynb` untuk mengunduh dataset `shrutimechlearn/churn-modelling` dan memuat file `Churn_Modelling.csv` menggunakan `pandas`.
- **28 Juni 2026**: tambahkan `EDA.ipynb` sebagai notebook EDA baru dengan pemeriksaan struktur data, preview, dan visualisasi awal.
- **1 Juni 2026**: tambahkan kelas terstruktur:
  - `DatasetDescription` untuk ukuran dataset, nama kolom, dan preview data.
  - `DataQualityCheck` untuk cek missing values, duplicate, dan tipe data.
  - `DescriptiveStatistics` untuk ringkasan statistik dan skewness kolom numerik.
  - `UnivariateAnalysis` untuk histogram, boxplot, dan countplot setiap fitur.
- **1 Juni 2026**: perbarui `README.md` dengan ringkasan pekerjaan, instruksi menjalankan, dan timeline tanggal spesifik.
- **1 Juni 2026**: hapus analisis univariat dari `EDA.ipynb`. 


## Struktur Kode dalam `EDA.ipynb`
- `kagglehub.dataset_download` untuk mengunduh file dataset.
- `pandas.read_csv` untuk memuat CSV.
- `df.info()` dan `df.head()` untuk melihat struktur dan contoh data.
- `DatasetDescription` untuk ringkasan awal dataset.
- `DataQualityCheck` untuk memverifikasi missing values, duplikat, dan tipe kolom.
- `DescriptiveStatistics` untuk ringkasan statistik numerik dan skewness.
- `UnivariateAnalysis` untuk plot distribusi dan identifikasi outlier.

## Cara Menjalankan
1. Pastikan Python terpasang.
2. Install library yang diperlukan:
   - `pip install kagglehub pandas numpy matplotlib seaborn scikit-learn`
3. Buka `EDA.ipynb` atau `cek data.ipynb` di Jupyter Notebook / Jupyter Lab / VS Code.
4. Jalankan sel kode secara berurutan.

## Library yang Dibutuhkan
- `kagglehub`
- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`

## Catatan
- `EDA.ipynb` sudah berisi pemeriksaan data lebih lengkap daripada notebook awal.
- Gunakan `EDA.ipynb` bila ingin memahami dataset secara menyeluruh sebelum preprocessing atau pemodelan.

## Sruktur Laporan khusus Algoritma Logika
- BAB 1 Pendahuluan:
   - 1.1 Latar Belakang (Pentingnya Retensi Pelanggan, Customer Churn Sebagai Permasalahan Data Mining, Pemanfaatan Machine Learning, Keterbatasan Metode Konvensional, Alasan Memilih LightGBM, Pentingnya Feature Engineering, )
   - 1.2 Rumusan Masalah:
      - Bagaimana karakteristik customer churn berdasarkan wilayah geografis nasabah?
      - Bagaimana performa algoritma LightGBM dalam memprediksi customer churn pada dataset nasabah bank?
      - Seberapa baik model LightGBM dalam mengklasifikasikan nasabah yang berpotensi churn - berdasarkan metrik evaluasi seperti Accuracy, Precision, Recall, F1-Score, dan ROC-AUC?
      - Variabel manakah yang memiliki kontribusi terbesar terhadap hasil prediksi churn berdasarkan analisis feature importance pada LightGBM?
   - 1.3 Tujuan Penelitian/Masalah:
      - Menganalisis karakteristik nasabah yang melakukan churn dan yang tetap menggunakan layanan bank.
      - Mengidentifikasi faktor-faktor yang memengaruhi customer churn.
      - Membangun model prediksi customer churn menggunakan algoritma LightGBM.
      - Mengevaluasi kinerja model LightGBM menggunakan berbagai metrik evaluasi klasifikasi.
      - Menentukan fitur-fitur yang paling berpengaruh terhadap customer churn berdasarkan feature importance.

- BAB 2 Isi:
   - 2.1 Pengambilan Data
   - 2.2 Pengumpulan Data
   - 2.3 Visualisasi Data
   - 2.4 Analisis
   - 2.5 Insight

- BAB 3 Penutup:
   - 3.1 Kesimpulan 