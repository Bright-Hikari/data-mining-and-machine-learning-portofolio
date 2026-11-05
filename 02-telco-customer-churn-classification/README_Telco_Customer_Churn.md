# Telco Customer Churn Classification

Proyek Machine Learning untuk memprediksi pelanggan telekomunikasi yang berpotensi berhenti berlangganan (*customer churn*).

## Tujuan
Membangun dan membandingkan tiga algoritma klasifikasi: Logistic Regression, Decision Tree, dan Random Forest. Evaluasi menggunakan Accuracy, Precision, Recall, F1-Score, dan Confusion Matrix. Interpretasi fitur menggunakan Permutation Feature Importance.

## Struktur Proyek
```text
02-telco-customer-churn-classification/
├── data/
│   ├── WA_Fn-UseC_-Telco-Customer-Churn.csv
│   ├── cleaned_telco_churn.csv
│   ├── model_evaluation_results.csv
│   └── feature_importance_results.csv
├── images/
├── models/
│   ├── logistic_regression.pkl
│   ├── decision_tree.pkl
│   └── random_forest.pkl
├── notebooks/
│   ├── 01_data_understanding.ipynb
│   ├── 02_exploratory_data_analysis.ipynb
│   ├── 03_data_cleaning_feature_engineering.ipynb
│   ├── 04_model_training.ipynb
│   ├── 05_model_evaluation.ipynb
│   └── 06_model_interpretation.ipynb
└── report/
    └── Laporan_Final_Telco_Customer_Churn.pdf
```
Catatan: file output di `data/`, `images/`, dan `models/` terbentuk setelah notebook dijalankan.

## Dataset
Dataset Telco Customer Churn. Target `Churn`: Yes = 1 dan No = 0. Letakkan CSV asli di folder `data/` dengan nama `WA_Fn-UseC_-Telco-Customer-Churn.csv`.

Sumber: [IBM Telco Customer Churn resources](https://github.com/IBM/telco-customer-churn-on-icp4d). Periksa ketentuan lisensi dan atribusi dataset sebelum distribusi.

## Alur Pengerjaan
1. Data Understanding.
2. Exploratory Data Analysis.
3. Data Cleaning & Feature Engineering.
4. Model Training.
5. Model Evaluation.
6. Model Interpretation.

## Hasil Evaluasi
| Model | Accuracy | Precision | Recall | F1-Score |
|---|---:|---:|---:|---:|
| Logistic Regression | **79.99%** | **65.44%** | **52.14%** | **58.04%** |
| Decision Tree | 77.36% | 58.46% | 50.80% | 54.36% |
| Random Forest | 79.56% | 64.43% | 51.34% | 57.14% |

Logistic Regression menjadi model terbaik berdasarkan empat metrik tersebut. Recall 52.14% menunjukkan masih ada pelanggan churn yang tidak terdeteksi.

## Top Feature Importance
| Feature | Importance |
|---|---:|
| tenure | 0.195386 |
| InternetService | 0.111788 |
| Contract | 0.111738 |
| OnlineSecurity | 0.031268 |
| TechSupport | 0.030313 |
| PaymentMethod | 0.019230 |
| OnlineBackup | 0.017469 |
| PaperlessBilling | 0.016415 |
| StreamingMovies | 0.013963 |
| MultipleLines | 0.009875 |

Nilai importance menunjukkan kontribusi fitur terhadap performa prediksi, bukan sebab-akibat.

## Menjalankan Proyek
```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```
Letakkan dataset pada folder `data/`, lalu jalankan notebook secara berurutan dari 01 sampai 06.

## Keterbatasan
- Recall model terbaik masih 52.14%.
- Evaluasi menggunakan satu pembagian train-test 80:20.
- Imputasi median `TotalCharges` pada versi awal dilakukan sebelum train-test split; sebaiknya dipindahkan ke pipeline yang di-fit hanya pada data training.
- Perlu cross-validation, hyperparameter tuning, dan evaluasi threshold.

## Laporan
Laporan PDF akhir berada di folder `report/`. Sebelum pengumpulan, tambahkan angka aktual Stage 1, grafik EDA Stage 2, dan confusion matrix Stage 5.
