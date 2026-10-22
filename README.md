# UTS Machine Learning: Linear Regression & Logistic Regression

Repositori ini dibuat untuk memenuhi Ujian Tengah Semester (UTS) mata kuliah Machine Learning yang diampu oleh Bapak Agung Perdananto S.Kom, M.Kom. Tugas ini berfokus pada implementasi algoritma Simple Linear Regression dan Logistic Regression menggunakan pustaka dasar NumPy (tanpa scikit-learn untuk model dan metrik utama) serta evaluasi kinerjanya pada dataset baru.

---

## 📌 Identitas Mahasiswa

- **Nama:** A Bintang Aril S
- **NIM:** 241011401317
- **Kelas:** REG B
- **Random State:** 17 (2 digit terakhir NIM)

---

## 📂 Struktur Repositori

```text
uts-machine-learning-241011401317/
├── README.md            # Ringkasan identitas, struktur repositori, dan hasil evaluasi
├── tugas_UTS.ipynb      # Notebook pengerjaan tugas UTS (kode, grafik, dan analisis)
├── Ads_Data.csv         # Dataset untuk Bagian A (Linear Regression)
└── Email_Data.csv       # Dataset untuk Bagian B (Logistic Regression)
```

---

## 🧮 Ringkasan Hasil Evaluasi

### 1. Bagian A – Linear Regression (`Ads_Data.csv`)

Model dilatih menggunakan metode **Normal Equation** dan diuji keterandalannya menggunakan **Gradient Descent** dengan beberapa variasi *learning rate*.

- **Metode:** Normal Equation
- **Metrik Evaluasi (Data Testing):**
  - **MAE:** Evaluasi rata-rata galat absolut prediksi penjualan.
  - **MSE:** Evaluasi galat kuadrat rerata.
  - **RMSE:** Rata-rata penyimpangan prediksi dalam satuan juta Rupiah.
  - **$R^2$ Score:** Tingkat kemampuan fitur `BiayaIklan` dalam menjelaskan variasi variabel `Penjualan`.
- **Eksperimen Gradient Descent:**
  - `LR = 0.001`: Terlalu lambat (butuh iterasi lebih banyak untuk konvergen).
  - `LR = 0.02`: Pembelajaran optimal dan konvergen secara stabil.
  - `LR = 0.1`: Terlalu tinggi, berisiko mengalami *overshooting* / *divergence*.

---

### 2. Bagian B – Logistic Regression (`Email_Data.csv`)

Model klasifikasi biner dilatih dengan **Gradient Descent** dan fungsi aktivasi **Sigmoid** untuk memprediksi kategori email (Spam / Bukan Spam).

- **Hyperparameter:** `learning_rate = 0.1`, `n_iterations = 10000`
- **Metrik Evaluasi (Data Testing, Threshold 0.5):**
  - **Accuracy:** Tingkat ketepatan klasifikasi keseluruhan.
  - **Precision:** Ketepatan dalam memprediksi email Spam (menjaga agar email penting tidak salah masuk ke folder Spam / *False Positive*).
  - **Recall:** Kemampuan menemukan seluruh email Spam yang ada.
  - **F1-Score:** Keseimbangan antara Precision dan Recall.
- **Eksperimen Threshold:**
  - Ambang batas (*threshold*) diuji pada nilai **0.3**, **0.5**, dan **0.7**.
  - Peningkatan threshold menaikkan nilai *Precision* dan menurunkan risiko *False Positive* yang dapat merugikan pengguna email.

---

## 🛠️ Cara Menjalankan Notebook

1. Pastikan pustaka yang dibutuhkan sudah terinstal: `numpy`, `pandas`, `matplotlib`.
2. Eksekusi seluruh sel di file `tugas_UTS.ipynb` (*Run All*) agar seluruh keluaran teks, tabel evaluasi, dan grafik visualisasi ter-generate secara lengkap.