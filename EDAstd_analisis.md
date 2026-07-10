# Penjelasan Notebook EDAstd

Notebook ini merupakan versi EDA yang lebih sederhana dan fokus pada pemeriksaan awal dataset. Tujuan utamanya adalah memahami struktur data, kualitas data, dan karakteristik statistik dasar sebelum lebih jauh ke tahap analisis atau pemodelan.

## Tujuan Notebook

Notebook ini dibuat untuk:
- melihat bentuk dataset;
- memeriksa missing value;
- melihat tipe data tiap kolom;
- melihat statistik deskriptif numerik;
- melakukan feature engineering ringan untuk membantu analisis churn.

## Isi Kode dan Maksudnya

### 1. Impor library
Notebook mengimpor library seperti pandas, numpy, matplotlib, dan seaborn untuk manipulasi data dan visualisasi.

### 2. Membaca dataset
Dataset dibaca dari file Churn_Modelling.csv lalu ditampilkan beberapa baris awal untuk melihat struktur data secara langsung.

### 3. Informasi dataset
Beberapa sel kode menampilkan:
- bentuk dataset (jumlah baris dan kolom);
- informasi kolom dan tipe data;
- jumlah missing value per kolom;
- ringkasan statistik deskriptif.

Langkah ini sangat penting karena memberi gambaran awal tentang kualitas data dan apakah ada masalah seperti missing value atau outlier.

### 4. Proses label churn
Notebook membuat kolom baru bernama Churn_Label untuk mengubah label numerik 0 dan 1 menjadi label yang lebih mudah dibaca, yaitu Non-Churn dan Churn.

### 5. Feature engineering sederhana
Notebook kemudian menghitung churn rate per kategori seperti:
- negara asal pelanggan;
- gender;
- status active member;
- kepemilikan kartu kredit;
- jumlah produk yang dimiliki.

Langkah ini membantu melihat apakah pola churn berbeda pada kelompok-kelompok tertentu.

### 6. Ringkasan churn
Notebook juga menghitung jumlah pelanggan, jumlah churn, dan rasio churn secara keseluruhan. Hasil ini penting untuk melihat apakah dataset memiliki distribusi target yang seimbang atau tidak.

## Penafsiran Data

Dari hasil analisis pada notebook ini, dapat diinterpretasikan bahwa:
- dataset tidak memiliki missing value, sehingga kualitas data secara umum baik;
- ada perbedaan rasio churn antar kelompok pelanggan;
- churn lebih sering terjadi pada pelanggan tertentu, terutama yang berasal dari negara tertentu atau yang tidak aktif sebagai anggota bank;
- pelanggan dengan jumlah produk yang lebih sedikit cenderung punya tingkat churn yang lebih tinggi;
- proporsi churn secara keseluruhan tidak terlalu kecil, sehingga data ini layak dipakai untuk pemodelan prediksi.

## Kesimpulan

Notebook EDAstd memberi gambaran awal yang kuat tentang dataset dan membantu memahami pola churn sebelum dilanjutkan ke tahap analisis lanjutan atau pemodelan. Notebook ini cocok dipakai sebagai versi EDA yang lebih ringkas namun tetap informatif.
