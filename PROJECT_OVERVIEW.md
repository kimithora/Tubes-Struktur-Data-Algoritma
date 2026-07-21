# Project Overview

## 1. Deskripsi Proyek

Proyek ini merupakan analisis prediksi **customer churn** menggunakan pendekatan Machine Learning pada dataset perbankan.

Customer churn merupakan kondisi ketika pelanggan berhenti menggunakan layanan suatu perusahaan. Dalam industri perbankan, kemampuan untuk mengidentifikasi pelanggan yang memiliki risiko churn sangat penting agar perusahaan dapat melakukan strategi retensi pelanggan secara lebih efektif.

Pada proyek ini dilakukan proses **Exploratory Data Analysis (EDA)**, analisis karakteristik pelanggan berdasarkan beberapa fitur utama, serta pembangunan model klasifikasi menggunakan **Logistic Regression** untuk memprediksi kemungkinan pelanggan melakukan churn.

---

# 2. Tujuan Analisis

Tujuan utama dari proyek ini adalah:

1. Menganalisis pola karakteristik pelanggan berdasarkan faktor demografi dan aktivitas layanan.
2. Mengidentifikasi faktor-faktor yang memiliki hubungan terhadap kemungkinan pelanggan melakukan churn.
3. Membangun model Machine Learning untuk melakukan klasifikasi pelanggan churn dan non-churn.
4. Mengevaluasi performa model berdasarkan metrik klasifikasi.
5. Memberikan insight yang dapat digunakan sebagai dasar strategi retensi pelanggan.

---

# 3. Dataset

Dataset yang digunakan adalah:

`Churn_Modelling.csv`

Dataset berisi informasi mengenai pelanggan bank dengan jumlah:

- Total data: **10.000 pelanggan**
- Target variabel:
  - `Exited`
    - 0 = Customer tidak churn
    - 1 = Customer churn

Beberapa fitur utama yang digunakan:

| Feature | Deskripsi |
|---|---|
| CreditScore | Skor kredit pelanggan |
| Geography | Negara tempat pelanggan berada |
| Gender | Jenis kelamin pelanggan |
| Age | Usia pelanggan |
| Tenure | Lama menjadi pelanggan |
| Balance | Saldo rekening pelanggan |
| NumOfProducts | Jumlah produk bank yang digunakan |
| HasCrCard | Kepemilikan kartu kredit |
| IsActiveMember | Status keaktifan pelanggan |
| EstimatedSalary | Estimasi pendapatan pelanggan |

---

# 4. Ringkasan Hasil Exploratory Data Analysis

## 4.1 Analisis Berdasarkan Negara (Geography)

| Negara | Total Customer | Churn | Churn Rate |
|---|---:|---:|---:|
| France | 5.014 | 810 | 16,15% |
| Germany | 2.509 | 814 | **32,44%** |
| Spain | 2.477 | 413 | 16,67% |

### Insight

Pelanggan dari **Germany memiliki tingkat churn tertinggi**, yaitu sebesar **32,44%**.

Nilai tersebut hampir dua kali lipat dibandingkan France dan Spain. Hal ini menunjukkan bahwa faktor geografis kemungkinan memiliki pengaruh terhadap keputusan pelanggan untuk meninggalkan layanan bank.

---

# 4.2 Analisis Berdasarkan Gender

| Gender | Total Customer | Churn | Churn Rate |
|---|---:|---:|---:|
| Female | 4.543 | 1.139 | **25,07%** |
| Male | 5.457 | 898 | 16,46% |

### Insight

Pelanggan perempuan memiliki tingkat churn lebih tinggi dibandingkan pelanggan laki-laki.

Perbedaan churn rate:

- Female: 25,07%
- Male: 16,46%

Hal ini menunjukkan adanya kemungkinan perbedaan perilaku penggunaan layanan berdasarkan gender.

---

# 4.3 Analisis Berdasarkan Status Keaktifan Member

| Status | Total Customer | Churn | Churn Rate |
|---|---:|---:|---:|
| Non-active Member | 4.849 | 1.302 | **26,85%** |
| Active Member | 5.151 | 735 | 14,27% |

### Insight

Status aktivitas pelanggan merupakan salah satu faktor paling kuat dalam analisis churn.

Pelanggan yang tidak aktif memiliki risiko churn hampir dua kali lebih tinggi dibandingkan pelanggan aktif.

Hal ini menunjukkan bahwa peningkatan engagement pelanggan dapat menjadi strategi penting untuk mengurangi churn.

---

# 4.4 Analisis Kepemilikan Credit Card

| Credit Card | Total Customer | Churn | Churn Rate |
|---|---:|---:|---:|
| Tidak Memiliki | 2.945 | 613 | 20,81% |
| Memiliki | 7.055 | 1.424 | 20,18% |

### Insight

Kepemilikan kartu kredit tidak menunjukkan perbedaan signifikan terhadap tingkat churn.

Customer yang memiliki kartu kredit maupun tidak memiliki kartu kredit memiliki tingkat churn yang relatif sama.

---

# 4.5 Analisis Berdasarkan Jumlah Produk

| Jumlah Produk | Total Customer | Churn | Churn Rate |
|---|---:|---:|---:|
| 1 Produk | 5.084 | 1.409 | 27,71% |
| 2 Produk | 4.590 | 348 | **7,58%** |
| 3 Produk | 266 | 220 | **82,71%** |
| 4 Produk | 60 | 60 | 0% |

### Insight

Jumlah produk memiliki pola yang menarik:

- Customer dengan **2 produk memiliki churn paling rendah**.
- Customer dengan **3 produk memiliki churn sangat tinggi (82,71%)**.
- Data pada jumlah produk 4 memiliki jumlah sampel sangat kecil sehingga perlu interpretasi hati-hati.

Hal ini menunjukkan bahwa jumlah produk tidak selalu meningkatkan loyalitas pelanggan. Penggunaan produk yang terlalu banyak dapat mengindikasikan adanya pelanggan dengan masalah tertentu.

---

# 5. Model Machine Learning

## Algoritma

Model yang digunakan:

**Logistic Regression**

Konfigurasi model:

```python
penalty='l2'
C=1.0
solver='lbfgs'
max_iter=1000
random_state=42
```

# 6. Evaluasi Model

Model Logistic Regression dievaluasi menggunakan beberapa metrik klasifikasi, yaitu:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

Evaluasi dilakukan pada dataset pengujian yang telah diseimbangkan antara kelas **Churn (1)** dan **Non-Churn (0)** agar model mampu mempelajari kedua kelas secara lebih optimal.

---

## 6.1 Classification Report

Hasil evaluasi model:

| Class | Precision | Recall | F1-score | Support |
|---|---:|---:|---:|---:|
| Non-Churn (0) | 0,69 | 0,72 | 0,70 | 1.593 |
| Churn (1) | 0,70 | 0,67 | 0,69 | 1.593 |
| **Accuracy** | | | **0,69** | 3.186 |

### Interpretasi

Berdasarkan hasil evaluasi:

- Model memperoleh **accuracy sebesar 69%**, yang menunjukkan bahwa model mampu melakukan klasifikasi dengan tingkat ketepatan yang cukup baik.
- Precision pada kelas churn mencapai **70%**, artinya sebagian besar pelanggan yang diprediksi churn memang benar-benar melakukan churn.
- Recall pada kelas churn sebesar **67%**, menunjukkan bahwa model berhasil mendeteksi sekitar 67% pelanggan yang benar-benar melakukan churn.
- Nilai F1-score sebesar **69%** menunjukkan keseimbangan antara kemampuan model dalam menemukan pelanggan churn dan menghindari kesalahan prediksi.

Performa antar kelas relatif seimbang sehingga model tidak terlalu condong hanya memprediksi kelas mayoritas.

---

# 6.2 Confusion Matrix

Hasil confusion matrix:

| | Predicted Non-Churn | Predicted Churn |
|---|---:|---:|
| Actual Non-Churn | 1142 | 451 |
| Actual Churn | 522 | 1071 |

Berdasarkan hasil tersebut:

### True Negative (TN)

**1142 pelanggan**

Model berhasil memprediksi pelanggan yang tetap bertahan sebagai non-churn.

---

### False Positive (FP)

**451 pelanggan**

Model memprediksi pelanggan akan churn, tetapi sebenarnya pelanggan masih bertahan.

Kesalahan ini dapat menyebabkan perusahaan melakukan strategi retensi kepada pelanggan yang sebenarnya tidak memiliki risiko churn.

---

### False Negative (FN)

**522 pelanggan**

Model gagal mendeteksi pelanggan yang benar-benar melakukan churn.

Kasus ini menjadi perhatian utama karena perusahaan kehilangan kesempatan untuk melakukan tindakan pencegahan.

---

### True Positive (TP)

**1071 pelanggan**

Model berhasil mendeteksi pelanggan yang benar-benar melakukan churn.

Hasil ini menunjukkan bahwa model cukup efektif dalam mengidentifikasi pelanggan berisiko.

---

# 7. Feature Importance

Feature importance dianalisis berdasarkan nilai absolut koefisien Logistic Regression.

Semakin besar nilai koefisien absolut, semakin besar kontribusi fitur terhadap keputusan klasifikasi model.

| Rank | Feature | Coefficient | Importance |
|---|---|---:|---:|
| 1 | Age | 0,835531 | 0,835531 |
| 2 | IsActiveMember | -0,461522 | 0,461522 |
| 3 | Geography_Germany | 0,360946 | 0,360946 |
| 4 | Gender_Male | -0,253054 | 0,253054 |
| 5 | Balance | 0,179989 | 0,179989 |
| 6 | CreditScore | -0,099346 | 0,099346 |
| 7 | NumOfProducts | -0,065473 | 0,065473 |
| 8 | EstimatedSalary | 0,036077 | 0,036077 |
| 9 | HasCrCard | -0,031676 | 0,031676 |
| 10 | Tenure | -0,023238 | 0,023238 |
| 11 | Geography_Spain | -0,003200 | 0,003200 |

---

# 8. Analisis Pengaruh Fitur

## 8.1 Age

Fitur **Age** menjadi variabel dengan pengaruh terbesar terhadap prediksi churn.

Koefisien positif menunjukkan bahwa peningkatan usia pelanggan berkorelasi dengan peningkatan kemungkinan churn.

Hal ini menunjukkan bahwa pelanggan dengan usia lebih tinggi perlu mendapatkan perhatian lebih dalam strategi retensi.

---

## 8.2 IsActiveMember

Status keaktifan pelanggan menjadi faktor penting kedua.

Koefisien negatif menunjukkan bahwa pelanggan aktif memiliki kecenderungan lebih rendah untuk melakukan churn.

Pelanggan yang jarang menggunakan layanan bank memiliki kemungkinan lebih tinggi untuk berhenti menggunakan layanan.

---

## 8.3 Geography_Germany

Variabel lokasi Germany memiliki pengaruh positif terhadap churn.

Hal ini sesuai dengan hasil eksplorasi sebelumnya dimana Germany memiliki churn rate tertinggi sebesar **32,44%**.

Customer dari wilayah ini dapat menjadi target utama dalam program peningkatan loyalitas.

---

## 8.4 Gender_Male

Gender memberikan pengaruh moderat terhadap model.

Meskipun bukan faktor utama, fitur ini tetap memberikan informasi tambahan dalam proses prediksi churn.

---

## 8.5 Balance

Saldo pelanggan memiliki pengaruh positif terhadap churn.

Pelanggan dengan saldo tinggi belum tentu memiliki loyalitas tinggi, sehingga perlu dianalisis bersama fitur lain seperti aktivitas penggunaan produk.

---

# 9. Insight Bisnis

Berdasarkan hasil analisis eksplorasi dan model Machine Learning, beberapa strategi yang dapat diterapkan:

## 1. Meningkatkan Engagement Customer

Karena pelanggan nonaktif memiliki churn rate lebih tinggi:

- Memberikan program loyalty.
- Mengirimkan personalisasi promosi.
- Meningkatkan penggunaan aplikasi atau layanan digital.

---

## 2. Fokus Retensi pada Customer Germany

Germany memiliki tingkat churn tertinggi.

Strategi yang dapat dilakukan:

- Analisis kebutuhan pelanggan regional.
- Memberikan layanan yang lebih personal.
- Mengevaluasi faktor penyebab ketidakpuasan pelanggan.

---

## 3. Monitoring Customer dengan Risiko Tinggi

Customer dengan karakteristik:

- Usia lebih tinggi.
- Tidak aktif menggunakan layanan.
- Berasal dari Germany.
- Memiliki pola penggunaan produk tertentu.

dapat dimasukkan ke dalam kategori pelanggan berisiko tinggi.

---

# 10. Kesimpulan

Berdasarkan keseluruhan proses analisis:

1. Dataset menunjukkan bahwa faktor demografi dan perilaku pelanggan memiliki hubungan terhadap kemungkinan churn.
2. Germany merupakan wilayah dengan tingkat churn tertinggi dibandingkan negara lainnya.
3. Customer yang tidak aktif memiliki risiko churn hampir dua kali lebih besar dibandingkan customer aktif.
4. Logistic Regression mampu melakukan klasifikasi churn dengan performa yang cukup seimbang dengan accuracy sebesar **69%**.
5. Faktor paling berpengaruh dalam prediksi churn adalah:
   - Age
   - IsActiveMember
   - Geography_Germany
   - Gender
   - Balance
6. Model dapat digunakan sebagai sistem awal untuk membantu perusahaan melakukan identifikasi pelanggan yang berpotensi meninggalkan layanan.

---

# 11. Struktur Repository

```text
├── Churn_Modelling.csv
│
├── cek data.ipynb
│   └── Pemeriksaan awal dataset
│       - Loading dataset
│       - Checking missing value
│       - Data dimension analysis
│
├── EDAstd.ipynb
│   └── Exploratory Data Analysis
│       - Statistik deskriptif
│       - Distribusi fitur
│       - Analisis karakteristik customer
│
├── EDAAlgo.ipynb
│   └── Machine Learning Pipeline
│       - Data preprocessing
│       - Feature engineering
│       - Model training
│       - Model evaluation
│
├── trialerror.ipynb
│   └── Eksperimen tambahan
│       - Testing metode
│       - Percobaan model
│       - Evaluasi alternatif
│
├── README.md
│   └── Dokumentasi utama repository
│
└── PROJECT_OVERVIEW.md
    └── Ringkasan analisis dan dokumentasi proyek