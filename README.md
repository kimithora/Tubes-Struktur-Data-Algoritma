# Tubes STD & Algo

# EKSPLORASI DATA DAN PEMODELAN LIGHTGBM UNTUK ANALISIS SERTA PREDIKSI CUSTOMER CHURN PADA DATA NASABAH PERBANKAN 
# EDA dan Analisis dengan LightGBM (Light Gradient Boosting Machine)

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
- **Awal Juni 2026**: tambahkan kelas terstruktur pada `EDA.ipynb` untuk memperjelas langkah EDA dan pemeriksaan kualitas data.
- **Awal Juni 2026**: beri penjelasan markdown tambahan pada beberapa sel di notebook agar alur analisis lebih mudah dipahami.
- **Pertengahan Juni 2026**: hapus analisis univariat dari `EDA.ipynb` untuk memisahkan fokus EDA dan model.
- **Pertengahan Juni 2026**: tambahkan catatan laporan di `README.md` agar mendukung dokumentasi tugas.
- **18 Juni 2026**: tambahkan rumusan masalah pada markdown `EDA.ipynb` untuk memperjelas tujuan analisis.
- **19 Juni 2026**: pisahkan file notebook untuk struktur data dan algoritma, sehingga konten EDA dan model menjadi lebih terorganisir.
- **19 Juni 2026**: tambahkan `trialerror.ipynb` untuk uji coba model regresi logistik dan analisis performa awal.
- **19 Juni 2026**: perbarui `README.md` dengan detail pembaruan terbaru, termasuk ringkasan `trialerror.ipynb`.
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

## Pembaruan `trialerror.ipynb`
`trialerror.ipynb` adalah notebook percobaan regresi logistik yang melakukan:

- Muat dataset `Churn_Modelling.csv` ke DataFrame `df`.
- Periksa struktur data, tipe kolom, dan missing values.
- Visualisasikan distribusi target churn `Exited` untuk memperlihatkan ketidakseimbangan kelas.
- Hapus kolom id yang tidak relevan: `RowNumber`, `CustomerId`, `Surname`.
- Transformasi fitur kategorikal `Geography` dan `Gender` menjadi variabel dummy dengan `pd.get_dummies(..., drop_first=True)`.
- Ubah nilai boolean ke integer bila ada kolom bertipe boolean.
- Pisahkan fitur `X` dan target `y`.
- Bagi data menjadi set pelatihan dan pengujian dengan perbandingan 80/20 serta stratifikasi target untuk menjaga proporsi churn.
- Standarisasi fitur numerik menggunakan `StandardScaler` agar regresi logistik dapat dilatih secara stabil.
- Visualisasikan fungsi sigmoid dan hubungan antara skor linear (`z`) dan probabilitas output.
- Latih model `LogisticRegression` pada data terstandarisasi.
- Prediksi probabilitas churn `y_prob` dan kelas target `y_pred`.
- Evaluasi model menggunakan metrik: accuracy, precision, recall, F1-score.
- Tampilkan confusion matrix, classification report, dan precision-recall curve.
- Analisis koefisien model dan odds ratio untuk menjelaskan pengaruh fitur terhadap churn.

### Hasil Utama dari `trialerror.ipynb`
- Accuracy: `0.808`
- Precision: `0.5891`
- Recall: `0.1867`
- F1 Score: `0.2836`

Confusion matrix pada data uji:
- True Negative (benar tidak churn): `1540`
- False Positive (diprediksi churn padahal tidak): `53`
- False Negative (diprediksi tidak churn padahal churn): `331`
- True Positive (benar churn): `76`

Dari classification report:
- Kelas 0 (tidak churn): precision 0.82, recall 0.97, F1-score 0.89.
- Kelas 1 (churn): precision 0.59, recall 0.19, F1-score 0.28.

### Interpretasi Hasil
- Akurasi model terlihat baik, tetapi sebagian besar prediksi benar karena kelas dominan adalah pelanggan tidak churn. Hal ini menunjukkan adanya ketidakseimbangan kelas yang memengaruhi metrik akurasi.
- Recall churn sangat rendah (`0.1867`), artinya model hanya mendeteksi sekitar 19% pelanggan yang sebenarnya churn. Dalam konteks churn prediction, recall rendah menjadi kelemahan penting karena banyak pelanggan churn terlewat.
- Precision churn moderat (`0.5891`), yang berarti sekitar 59% prediksi churn benar. Model cukup konservatif dalam memprediksi churn.
- ROC AUC `0.7748` menunjukkan model masih lebih baik daripada tebakan acak untuk memisahkan kelas churn dan non-churn, tetapi belum cukup kuat untuk penggunaan produksi tanpa peningkatan.
- Precision-recall curve membantu menilai trade-off antara deteksi churn dan tingkat kesalahan prediksi churn.

### Interpretasi Fitur
- Fitur dengan koefisien positif paling besar menunjukkan peningkatan probabilitas churn:
  - `Age`
  - `Geography_Germany`
  - `Balance`
  - `EstimatedSalary`
  - `Geography_Spain`
- Fitur dengan koefisien negatif menunjukkan kontribusi terhadap penurunan peluang churn:
  - `IsActiveMember`
  - `Gender_Male`
  - `CreditScore`
  - `NumOfProducts`
  - `HasCrCard`
  - `Tenure`

- `Age` memiliki odds ratio tertinggi (`2.09`), yang menunjukkan bahwa peningkatan pada variabel usia berhubungan dengan peningkatan odds churn dalam model ini.
- `IsActiveMember` memiliki odds ratio terendah (`0.597`), yang menandakan bahwa nasabah yang aktif cenderung lebih kecil kemungkinan churn.

### Kesimpulan Tambahan
- `trialerror.ipynb` menyajikan eksperimen awal regresi logistik untuk prediksi churn.
- Model saat ini cocok untuk mempelajari hubungan fitur dan perilaku churn, tetapi perlu perbaikan untuk mendeteksi churn dengan lebih baik.
- Rekomendasi perbaikan: tangani ketidakseimbangan kelas (misalnya oversampling/undersampling), pertimbangkan algoritma non-linear seperti LightGBM, dan optimalkan threshold klasifikasi untuk meningkatkan recall churn.

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
