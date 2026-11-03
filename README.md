# 🛍️ Customer Segmentation and Predictive Classification

Proyek ini bertujuan untuk melakukan **segmentasi pelanggan** menggunakan teknik *Unsupervised Learning* (**K-Means Clustering** & **PCA**) dan membangun **model klasifikasi prediktif** menggunakan *Supervised Machine Learning* untuk mengidentifikasi karakteristik serta memprediksi profil kelompok pelanggan secara akurat.

---

## 📑 Daftar Isi

- [Struktur Dataset](#-struktur-dataset)
- [Alur Kerja Proyek](#-alur-kerja-proyek-workflow)
- [Tech Stack & Libraries](#️-tech-stack--libraries)
- [Hasil Analisis Singkat](#-hasil-analisis-singkat-eda-highlights)
- [Cara Menjalankan Proyek](#-cara-menjalankan-proyek)

---

## 📂 Struktur Dataset

Dataset yang digunakan berisi informasi demografi dan sosio-ekonomi dari **2.000 pelanggan** dengan **8 kolom awal** (kolom `ID` dihapus sebelum pemodelan).

| Kolom | Tipe Data | Keterangan / Arti Nilai |
|---|---|---|
| `Sex` | Kategorikal | 0 = Laki-laki, 1 = Perempuan |
| `Marital status` | Kategorikal | 0 = Lajang, 1 = Menikah / Punya Pasangan |
| `Age` | Numerik | Usia pelanggan (tahun) |
| `Education` | Ordinal | 0 = Lainnya/Tidak Diketahui, 1 = SMA, 2 = Universitas, 3 = Pascasarjana |
| `Income` | Numerik | Pendapatan tahunan |
| `Occupation` | Ordinal | 0 = Pengangguran/Tidak Terampil, 1 = Terampil/Pegawai, 2 = Manajemen/Wiraswasta |
| `Settlement size` | Ordinal | 0 = Kota Kecil, 1 = Kota Sedang, 2 = Kota Besar |

---

## 🚀 Alur Kerja Proyek (Workflow)

### 1. Eksplorasi Data (EDA) & Pembersihan Data
- Memeriksa bentuk dataset, tipe data, *missing values*, dan duplikasi.
- Menganalisis distribusi fitur numerik (`Age`, `Income`) dan fitur kategorikal.
- Menghapus kolom `ID` karena tidak memberikan informasi prediktif pada model.

### 2. Feature Engineering & Normalisasi
- Menerapkan **MinMaxScaler** untuk menyamakan skala fitur sebelum proses *clustering*.

### 3. Customer Segmentation (Unsupervised Learning)
- Menerapkan **K-Means Clustering** untuk mengelompokkan pelanggan berdasarkan kemiripan karakteristik.
- Mengevaluasi kualitas cluster menggunakan **Silhouette Score**.
- Mereduksi dimensi data menggunakan **PCA (Principal Component Analysis)** untuk visualisasi cluster.

### 4. Predictive Modeling (Supervised Learning)
- Membagi data menjadi *train set* dan *test set*.
- Melatih model klasifikasi **Random Forest Classifier** dan **Gradient Boosting Classifier** untuk memprediksi segmen atau kategori pelanggan.
- Mengevaluasi performa model menggunakan **Confusion Matrix**, **Classification Report**, dan **Accuracy Score**.

---

## 🛠️ Tech Stack & Libraries

Proyek ini dikembangkan menggunakan bahasa **Python** dengan pustaka sains data berikut:

| Kategori | Library |
|---|---|
| Manipulasi & Analisis Data | Pandas, NumPy |
| Visualisasi Data | Matplotlib, Seaborn |
| Machine Learning | Scikit-Learn (`KMeans`, `PCA`, `MinMaxScaler`, `RandomForestClassifier`, `GradientBoostingClassifier`, `train_test_split`, `metrics`) |
| Statistik | SciPy (`scipy.stats`) |

---

## 📊 Hasil Analisis Singkat (EDA Highlights)

- **Distribusi Usia & Pendapatan:** Sebagian besar pelanggan berada pada rentang usia produktif awal dengan variasi tingkat pendapatan tahunan yang cukup signifikan.
- **Korelasi:** Ditemukan korelasi positif yang moderat antara usia (`Age`) dan pendapatan (`Income`) pelanggan.

---

## 💻 Cara Menjalankan Proyek

1. **Instal pustaka yang diperlukan:**

   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn scipy
   ```

2. **Siapkan dataset.** Letakkan file `segmentation_data.csv` di dalam folder `../raw_data/` relatif terhadap direktori script/notebook Anda:

   ```
   .
   ├── raw_data/
   │   └── segmentation_data.csv
   └── notebook/
       └── customer_segmentation.ipynb
   ```

3. **Jalankan Jupyter Notebook** secara berurutan dari sel pertama hingga selesai.

---
