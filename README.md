# Analisis Kualitas Teh Berbasis Data Sensor Aroma

## Latar Belakang Masalah
Penilaian kualitas teh sering kali bergantung pada evaluasi sensorik yang bersifat
subjektif. Dengan adanya data sensor aroma, proses evaluasi kualitas dapat
didukung oleh analisis berbasis data untuk meningkatkan konsistensi dan
standarisasi penilaian mutu.

Proyek ini bertujuan untuk menganalisis dan mengklasifikasikan kualitas/jenis teh
berdasarkan sinyal aroma yang direkam oleh sensor gas, guna mendukung
pengambilan keputusan dalam pengendalian kualitas produk.

---

## Data
- **Sumber dataset:**  
  https://github.com/wicaksonoleksono/data_teh
- **Unit analisis:** Sampel teh
- **Bentuk data:**  
  Setiap sampel direpresentasikan oleh file `.csv` berukuran
  **3000 baris × 6 sensor**
- **Sensor yang digunakan:**
  - MQ-7
  - MQ-9
  - TGS 822
  - TGS 2600
  - TGS 2602
  - TGS 2611

Dataset dibagi menjadi:
- `train/` → data latih
- `test/` → data uji

---

## Pendekatan Analisis

### 1. Pra-pemrosesan Data
- Pemrosesan sinyal aroma dari enam sensor gas
- Penyiapan data untuk ekstraksi fitur statistik

### 2. Ekstraksi Fitur
Dari setiap sensor diekstraksi fitur statistik berikut:
- Mean
- Standar deviasi
- Nilai maksimum
- Nilai minimum
- Skewness
- Kurtosis

Total fitur per sampel:
**6 sensor × 6 fitur = 36 fitur**

### 3. Analisis Klasifikasi
- Penerapan model klasifikasi untuk memprediksi kualitas/jenis teh
- Model yang digunakan:
  - Random Forest
  - XGBoost
- Evaluasi performa menggunakan metrik klasifikasi standar

---

## Hasil Analisis
- Data sensor aroma mampu membedakan kualitas/jenis teh secara konsisten.
- Fitur statistik dari sinyal sensor memberikan representasi yang cukup
  untuk mendukung proses klasifikasi.
- Model klasifikasi menunjukkan performa yang baik pada data uji,
  sehingga berpotensi digunakan sebagai alat bantu quality control.

---

## Insight Utama
- Kualitas teh dapat dianalisis secara objektif menggunakan data sensor aroma.
- Pendekatan berbasis data membantu mengurangi subjektivitas dalam
  proses penilaian mutu produk.
- Identifikasi fitur penting dapat digunakan sebagai dasar
  perbaikan proses produksi dan pengendalian kualitas.

---

## Rekomendasi
- **Pengendalian Kualitas:**  
  Data sensor dan model klasifikasi dapat digunakan sebagai
  alat bantu evaluasi mutu produk teh.
- **Standarisasi Penilaian:**  
  Pendekatan ini mendukung penilaian kualitas yang lebih konsisten
  dibandingkan evaluasi manual semata.
- **Pengembangan Lanjutan:**  
  Analisis dapat diperluas dengan pendekatan interpretabilitas model
  atau pemodelan sekuens waktu untuk sinyal mentah.

---

## Evaluasi Model
Evaluasi dilakukan menggunakan:
- Precision, Recall, dan F1-score
- Confusion Matrix
- Akurasi pada data uji

---

## Tools & Library
- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- Matplotlib, Seaborn

---

## Struktur Proyek
```
tea-quality-classification/
├── data_teh/
├── data_teh_split/
│   ├── train/
│   └── test/
├── train_dataset.csv
├── test_dataset.csv
├── output/
│   ├── model_teh.pkl
│   └── model_xgb_teh.pkl
├── main.py
├── train_model.py
├── train_model_xgboost.py
├── predict_teh.py
├── src/
│   ├── preprocess.py
│   ├── build_dataset.py
│   └── splitting_data.py
└── README.md
```
---

## Penulis

Yayang Matira | Mahasiswa Magister Ilmu Komputer | Universitas Gadjah Mada
