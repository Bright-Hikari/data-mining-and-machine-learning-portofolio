# Analisis Regresi Linear — Prediksi Perkembangan Diabetes

## Tentang proyek ini
Proyek ini dibuat untuk latihan Machine Learning dengan metode **regresi**. Kita akan mencoba beberapa model regresi linear, membandingkan hasilnya, lalu memilih model yang paling sesuai berdasarkan performanya pada data pengujian.

Dataset yang digunakan adalah **Diabetes dataset** dari Scikit-learn. Dataset ini berisi 442 data, 10 fitur, dan satu target angka yang menggambarkan ukuran perkembangan diabetes satu tahun setelah pengukuran awal.

> **Catatan penting:** Proyek ini hanya untuk pembelajaran dan latihan analisis data. Modelnya bukan alat diagnosis atau rekomendasi medis, dan tidak boleh digunakan untuk mengambil keputusan kesehatan seseorang.

## Tujuan analisis
Memprediksi nilai `target` menggunakan 10 fitur yang tersedia, kemudian membandingkan beberapa pendekatan regresi untuk melihat model mana yang menghasilkan prediksi paling baik pada data yang belum pernah dilihat model.

## Bagian yang dibahas
Proyek ini mencakup lima bagian utama sesuai instruksi tugas:

1. **Data Summary** — mengenal ukuran dataset, fitur, dan target yang akan diprediksi.
2. **Objective of the Analysis** — menjelaskan tujuan analisis.
3. **Model Comparison** — membandingkan beberapa variasi regresi.
4. **Key Findings** — merangkum temuan penting dari hasil pemodelan.
5. **Limitations and Next Steps** — membahas kekurangan analisis dan hal yang bisa dikembangkan.

## Struktur folder
```text
linear-regression-project/
├── README.md
├── requirements.txt
├── .gitignore
├── data/
│   ├── diabetes_progression.csv
│   └── data_dictionary.csv
├── notebooks/
│   └── 01_linear_regression_analysis.ipynb
├── results/
│   ├── benchmark_metrics.csv
│   └── benchmark_note.txt
└── report/
    └── REPORT_TEMPLATE.md
```

## Mengenal dataset
Dataset memiliki:
- **442 baris data**
- **10 fitur input:** `age`, `sex`, `bmi`, `bp`, `s1`, `s2`, `s3`, `s4`, `s5`, dan `s6`
- **1 target:** `target`, yaitu ukuran numerik perkembangan penyakit satu tahun setelah pengukuran awal.

Nilai fitur pada dataset ini sudah melalui proses standardisasi dari sumbernya. Jadi, angkanya tidak bisa langsung dibaca sebagai satuan asli seperti kilogram atau tekanan darah dalam mmHg.

File `data/data_dictionary.csv` berisi ringkasan arti setiap kolom. Dataset juga disertakan dalam repository, sehingga notebook bisa dijalankan tanpa perlu mengunduh data lagi.

Sumber dan penjelasan dataset:
https://scikit-learn.org/stable/datasets/toy_dataset.html#diabetes-dataset

## Model yang dibandingkan
Notebook membandingkan beberapa pendekatan berikut:

- **Mean Baseline:** model pembanding sederhana yang selalu memprediksi nilai rata-rata target dari data latih.
- **Simple Linear Regression:** regresi linear sederhana yang hanya menggunakan fitur `bmi`.
- **Multiple Linear Regression:** regresi linear yang menggunakan seluruh 10 fitur.
- **Polynomial Regression:** menambahkan kombinasi fitur berpangkat hingga derajat dua agar model bisa menangkap pola yang lebih melengkung.
- **Ridge Regression:** regresi dengan regularisasi L2 untuk membantu mengendalikan besar koefisien.
- **Lasso Regression:** regresi dengan regularisasi L1 yang juga dapat mengecilkan koefisien fitur.

## Cara menjalankan proyek

### 1. Ekstrak atau clone repository
Jika menggunakan ZIP, ekstrak terlebih dahulu. Jika menggunakan Git:
```bash
git clone <URL_REPOSITORY_GITHUB>
cd linear-regression-project
```

### 2. Buat virtual environment
Windows PowerShell:
```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

macOS/Linux:
```bash
python -m venv .venv
source .venv/bin/activate
```

### 3. Install library yang dibutuhkan
```bash
python -m pip install -r requirements.txt
```

### 4. Jalankan Jupyter Notebook
```bash
jupyter notebook
```
Buka `notebooks/01_linear_regression_analysis.ipynb`, lalu jalankan semua cell dari atas sampai bawah.

## Cara membaca hasil evaluasi
Model dinilai menggunakan tiga metrik:

- **MAE:** rata-rata selisih absolut antara nilai asli dan prediksi. Semakin kecil, semakin baik.
- **RMSE:** mirip MAE, tetapi memberi penalti lebih besar pada kesalahan yang jauh. Semakin kecil, semakin baik.
- **R²:** menunjukkan seberapa besar variasi target yang dapat dijelaskan model pada data pengujian. Nilai yang lebih tinggi umumnya lebih baik.

Pemilihan model terutama menggunakan nilai RMSE terendah, lalu mempertimbangkan MAE dan R² sebagai pendukung. Hasil pada `results/benchmark_metrics.csv` merupakan hasil awal yang sudah dihitung. Jalankan kembali notebook untuk memeriksa dan menghasilkan ulang hasilnya di perangkat sendiri.

## Batasan analisis
- Dataset relatif kecil, yaitu 442 baris.
- Fitur sudah distandardisasi sehingga tidak langsung menunjukkan satuan aslinya.
- Hasil dari satu kali pembagian data bisa berubah jika pembagian data berbeda.
- Model linear mungkin belum mampu menangkap semua pola yang kompleks.
- Hubungan antarvariabel tidak otomatis berarti hubungan sebab-akibat.
- Dataset ini tidak ditujukan untuk penggunaan klinis.

## Pengembangan selanjutnya
Analisis dapat dikembangkan dengan validasi silang berulang, pemeriksaan data yang berpengaruh besar, analisis residual lebih lanjut, dan perbandingan dengan model non-linear sebagai eksperimen tambahan.

## Atribusi
Dataset disediakan melalui Scikit-learn. Silakan baca dokumentasi sumber untuk informasi lengkap mengenai asal dan ketentuan penggunaan dataset.
