# Proyek Machine Learning: Clustering & Klasifikasi Data Nasabah

**Oleh: Anggoro Dwi Prasetyo**

Repository ini berisi submission akhir untuk proyek Machine Learning yang mencakup dua tugas utama:
1.  **Unsupervised Learning (Clustering):** Melakukan segmentasi nasabah berdasarkan perilaku transaksi dan demografi.
2.  **Supervised Learning (Klasifikasi):** Membangun model prediksi untuk mengklasifikasikan nasabah ke dalam cluster yang telah terbentuk.

---

## Struktur File

Berikut adalah penjelasan mengenai file-file yang terdapat dalam proyek ini:

### 1. Notebook Utama
* `[Clustering]_Submission_Akhir_BMLP_Anggoro_Dwi_Prasetyo.ipynb`: Notebook yang berisi proses cleaning data, EDA, preprocessing, hingga pemodelan K-Means Clustering dan interpretasi hasil.
* `[Klasifikasi]_Submission_Akhir_BMLP_Anggoro_Dwi_Prasetyo.ipynb`: Notebook yang berisi pembangunan model klasifikasi (Decision Tree & Random Forest) menggunakan label yang dihasilkan dari proses clustering.

### 2. Dataset
* `data_clustering.csv`: Data hasil preprocessing (scaled) yang sudah memiliki label cluster (Target). Digunakan untuk training model klasifikasi.
* `data_clustering_inverse.csv`: Data dengan nilai asli (tanpa scaling) yang sudah memiliki label cluster. Digunakan untuk interpretasi bisnis dan analisis karakteristik nasabah.

### 3. Model Tersimpan (Saved Models)
File-file ini berisi model yang sudah dilatih dan disimpan menggunakan `joblib`:
* `model_clustering.h5`: Model K-Means yang sudah dilatih.
* `PCA_model_clustering.h5`: Model PCA (jika digunakan untuk reduksi dimensi).
* `decision_tree_model.h5`: Model klasifikasi Decision Tree (Baseline).
* `explore_random_forest_classification.h5`: Model Random Forest dari hasil eksplorasi.
* `tuning_classification.h5`: Model klasifikasi terbaik setelah proses Hyperparameter Tuning.

---

## Hasil Analisis & Interpretasi

### 1. Profil Cluster (Customer Segmentation)
Berdasarkan hasil pemodelan Clustering, ditemukan 3 segmen nasabah utama:

* **Cluster 0 (Nasabah Standar / Moderate User):**
    * Memiliki rata-rata nilai transaksi dan saldo akun yang berada sedikit di bawah rata-rata global.
    * Merepresentasikan profil nasabah reguler dengan aktivitas perbankan standar.
* **Cluster 1 (Nasabah Muda Aktif / Young Active User):**
    * Didominasi oleh nasabah dengan usia paling muda.
    * Memiliki rata-rata nilai transaksi tertinggi namun dengan durasi transaksi yang cepat.
    * Merepresentasikan nasabah produktif yang efisien.
* **Cluster 2 (Nasabah Mapan / Mature Saver):**
    * Berisi nasabah dengan usia paling matang (senior).
    * Memiliki rata-rata saldo akun (`AccountBalance`) tertinggi dibandingkan kelompok lain.
    * Cenderung menyimpan dana dalam jumlah besar.

### 2. Performa Model Klasifikasi
Untuk memprediksi segmen nasabah baru, dikembangkan model klasifikasi dengan hasil evaluasi sebagai berikut:
* **Akurasi Model:** ~98% (Berdasarkan evaluasi pada dataset uji).
* **Model Terbaik:** Random Forest (setelah Hyperparameter Tuning).

---

## Requirements

Untuk menjalankan notebook ini, diperlukan library Python berikut:
* Python 3.x
* Pandas
* NumPy
* Scikit-Learn
* Matplotlib
* Seaborn
* Joblib

## Cara Menjalankan
1.  Pastikan semua file berada dalam satu direktori.
2.  Jalankan notebook Clustering terlebih dahulu untuk menghasilkan file output CSV dan model clustering.
3.  Jalankan notebook Klasifikasi untuk melatih model prediksi berdasarkan data hasil clustering.

---
*Submission Akhir - Belajar Machine Learning untuk Pemula*
