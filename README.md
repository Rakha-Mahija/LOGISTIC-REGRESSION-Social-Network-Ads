# Social Network Ads Prediction using Logistic Regression

## 📌 Project Overview
Proyek ini bertujuan untuk membangun model klasifikasi biner menggunakan algoritma **Logistic Regression** untuk memprediksi apakah seorang pengguna akan membeli produk (**Purchased**) setelah melihat iklan di jejaring sosial. Prediksi didasarkan pada dua fitur utama: **Umur (Age)** dan **Perkiraan Gaji (Estimated Salary)** [history, 334].

Solusi ini mendemonstrasikan alur kerja data science ujung-ke-ujung (end-to-end), mulai dari pengambilan dataset langsung dari Kaggle hingga evaluasi performa model yang mendalam.

## 📊 Dataset
*   **Sumber:** [Kaggle - Social Network Ads](https://www.kaggle.com/datasets/dragonheir/logistic-regression)
*   **Fitur ($X$):** `Age`, `EstimatedSalary` [history].
*   **Target ($y$):** `Purchased` (0: Tidak Membeli, 1: Membeli) [history].
*   **Metode Load:** Menggunakan library `kagglehub` untuk integrasi langsung [history, 146].

## 🛠️ Tech Stack
*   **Language:** Python
*   **Libraries:** 
    *   `pandas` & `numpy` (Manipulasi Data)
    *   `scikit-learn` (Modeling & Evaluasi)
    *   `kagglehub` (Dataset Access)
    *   `matplotlib` (Visualisasi)

## 🚀 Workflow
1.  **Data Acquisition:** Mengunduh dataset terbaru menggunakan API `kagglehub`.
2.  **Data Splitting:** Membagi data menjadi 70% Training set dan 30% Test set (`random_state=0`) [history, 292].
3.  **Feature Scaling:** Menerapkan `StandardScaler` untuk menstandarisasi rentang nilai fitur agar model Logistic Regression dapat konvergen dengan optimal [history, 333].
4.  **Model Training:** Melatih model Logistic Regression menggunakan Scikit-Learn.
5.  **Model Interpretation:** Menganalisis koefisien model dan *Odds Ratio* untuk memahami pengaruh fitur terhadap peluang pembelian [history, 273].
6.  **Evaluation:** Menguji model pada data yang belum pernah dilihat (*unseen data*).

## 📈 Performance Results
Model Logistic Regression menunjukkan performa yang **sangat baik** dengan hasil sebagai berikut:

*   **Accuracy:** **88%** [history].
*   **Confusion Matrix:**
    *   **True Negative (TN):** 74
    *   **False Positive (FP):** 5
    *   **False Negative (FN):** 10
    *   **True Positive (TP):** 31 [history, 340].

### Classification Report:
| Class | Precision | Recall | F1-Score | Support |
| :--- | :--- | :--- | :--- | :--- |
| 0 (No) | 0.88 | 0.94 | 0.91 | 79 |
| 1 (Yes) | 0.86 | 0.76 | 0.81 | 41 |

## 🔍 Key Insights
1.  **Kinerja Model:** Model sangat mahir dalam mengidentifikasi pengguna yang tidak membeli (Recall 0.94 pada kelas 0), namun masih memiliki peluang untuk diperbaiki dalam mendeteksi calon pembeli aktual (Recall 0.76 pada kelas 1) [history, 344].
2.  **Feature Importance:** Berdasarkan koefisien model, Umur dan Gaji memiliki korelasi positif yang kuat terhadap keputusan pembelian [history].
3.  **Efektivitas Scaling:** Tanpa *Feature Scaling*, model cenderung bias. Penerapan standarisasi secara signifikan memperbaiki kemampuan prediksi model [history, 110].
