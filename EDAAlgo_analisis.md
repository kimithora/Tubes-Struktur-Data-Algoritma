# Penjelasan Notebook EDAAlgo

Notebook ini berfokus pada eksplorasi data customer churn secara lebih terstruktur. Tujuan utamanya adalah membantu memahami pola pelanggan yang cenderung churn dan menyiapkan dasar analisis sebelum masuk ke tahap pemodelan.

## Tujuan Notebook

Notebook ini dibuat untuk:
- membaca dataset customer bank dari file Churn_Modelling.csv;
- memeriksa struktur data secara umum;
- menyiapkan fitur tambahan yang membantu analisis churn;
- melihat pola churn berdasarkan kategori tertentu seperti negara, gender, status keanggotaan, dan jenis produk.

## Isi Kode dan Maksudnya

### 1. Impor library
Kode pertama mengimpor library yang dibutuhkan, seperti pandas, numpy, matplotlib, dan seaborn. Library ini dipakai untuk memproses data, membuat tampilan tabel, dan membuat visualisasi.

### 2. Membaca dataset
Notebook memuat file CSV ke dalam DataFrame. Langkah ini penting karena seluruh analisis berjalan dari data yang sudah diimport.

### 3. Feature engineering
Bagian ini adalah inti dari notebook. Kode membuat beberapa kolom baru yang berisi churn rate berdasarkan kelompok tertentu, misalnya:
- churn rate per negara (Geography);
- churn rate per gender;
- churn rate berdasarkan status active member;
- churn rate berdasarkan apakah pelanggan punya kartu kredit;
- churn rate berdasarkan jumlah produk yang dimiliki.

Tujuan dari langkah ini adalah untuk melihat apakah ada kelompok pelanggan tertentu yang cenderung lebih mudah churn.

### 4. Kelas EDAAnalysis
Bagian ini berisi beberapa fungsi untuk menampilkan:
- bentuk dataset (shape);
- informasi kolom dan tipe data;
- missing value;
- statistik deskriptif numerik;
- ringkasan total pelanggan, churn, dan non-churn.

Fungsi ini membantu menganalisis data secara sistematis dan lebih mudah dibaca.

### 5. Kelas Visualization
Bagian terakhir notebook membuat visualisasi sederhana berupa pie chart untuk:
- proporsi pelanggan churn dan non-churn secara keseluruhan;
- proporsi churn berdasarkan negara.

Visualisasi ini membantu pembaca melihat pola secara cepat tanpa harus membaca angka saja.

## Penafsiran Data

Dari hasil analisis yang dilakukan, notebook menunjukkan beberapa temuan penting:
- jumlah pelanggan dalam dataset cukup besar, sehingga pola churn bisa dianalisis secara lebih representatif;
- churn tidak terjadi secara merata di semua kelompok;
- pelanggan dari negara tertentu punya peluang churn yang lebih tinggi dibanding negara lain;
- pelanggan yang tidak aktif secara finansial atau tidak aktif sebagai anggota cenderung lebih besar kemungkinan churn-nya;
- jumlah produk yang dimiliki juga bisa menjadi sinyal penting karena pelanggan dengan jumlah produk tertentu menunjukkan tingkat churn yang berbeda.

## Kesimpulan

Notebook EDAAlgo cocok dipakai untuk memahami karakteristik awal pelanggan yang berpotensi churn. Hasil dari notebook ini tidak hanya menunjukkan apakah churn terjadi, tetapi juga mengapa churn lebih sering terjadi pada kelompok tertentu.
