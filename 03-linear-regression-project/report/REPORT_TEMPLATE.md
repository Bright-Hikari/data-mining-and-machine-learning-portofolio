# Template Laporan — Analisis Regresi Linear

## 1. Ringkasan Dataset
Dataset Diabetes dari Scikit-learn memiliki 442 baris data, 10 fitur input, dan satu target numerik. Target tersebut merupakan ukuran perkembangan diabetes satu tahun setelah pengukuran awal. Seluruh fitur input sudah distandardisasi. Penjelasan kolom dapat dilihat pada `../data/data_dictionary.csv`.

## 2. Tujuan Analisis
Analisis ini bertujuan memprediksi nilai target menggunakan fitur-fitur yang tersedia, lalu membandingkan beberapa variasi regresi untuk menentukan model dengan hasil prediksi terbaik pada data pengujian.

## 3. Perbandingan Model
Model yang dibandingkan adalah Mean Baseline, Simple Linear Regression, Multiple Linear Regression, Polynomial Regression derajat dua, Ridge Regression, dan Lasso Regression.

Isi tabel berikut setelah menjalankan notebook:

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Mean Baseline | — | — | — |
| Simple Linear Regression (BMI) | — | — | — |
| Multiple Linear Regression | — | — | — |
| Polynomial Regression (degree 2) | — | — | — |
| Ridge Regression | — | — | — |
| Lasso Regression | — | — | — |

Jelaskan model mana yang dipilih dan alasan pemilihannya. Dalam proyek ini, RMSE digunakan sebagai patokan utama, dengan MAE dan R² sebagai metrik pendukung.

## 4. Temuan Utama
Tuliskan 2–4 temuan berdasarkan hasil notebook. Misalnya:
- Model dengan nilai RMSE paling rendah.
- Perbandingan model terpilih dengan Mean Baseline.
- Apakah Ridge atau Lasso memberikan peningkatan dibanding regresi linear biasa.
- Fitur atau pola yang terlihat menonjol dari hasil interpretasi model.

Pastikan setiap temuan didukung oleh angka atau grafik dari notebook. Koefisien model menunjukkan hubungan dalam model, bukan bukti bahwa suatu fitur menyebabkan perubahan target.

## 5. Keterbatasan dan Pengembangan Selanjutnya
Bahas ukuran dataset yang relatif kecil, fitur yang sudah distandardisasi, kemungkinan perubahan hasil karena pembagian data, keterbatasan model linear, dan perlunya validasi lebih lanjut. Dataset ini hanya untuk pembelajaran, bukan untuk mengambil keputusan medis.

## 6. Kesimpulan
Rangkum tujuan analisis, model yang terpilih, alasan pemilihan berdasarkan metrik pengujian, temuan utama, serta hal-hal yang masih perlu diperbaiki.
