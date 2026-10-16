# UTS Machine Learning — Rangga Afandi

- Nama: Rangga Afandi
- NIM: 241011400510
- Kelas: Reg B

## Isi Repositori

| File | Keterangan |
|---|---|
| `tugas_UTS.ipynb` | Notebook pengerjaan Linear Regression & Logistic Regression |
| `Ads_Data.csv` | Dataset biaya iklan vs penjualan (40 data) |
| `Email_Data.csv` | Dataset klasifikasi email spam (60 data) |
| `README.md` | Dokumentasi repositori ini |

## Cara Menjalankan

1. Pastikan Python 3 dan Jupyter Notebook sudah terinstall
2. Install library yang dibutuhkan:
   pip install numpy pandas matplotlib scikit-learn
3. Simpan semua file di folder yang sama
4. Buka `tugas_UTS.ipynb` di Jupyter Notebook atau VS Code
5. Klik Run All untuk menjalankan semua sel
6. Semua output dan grafik akan muncul

Catatan: Bagian bonus menggunakan scikit-learn sesuai izin pada instruksi tugas. Bagian utama mengimplementasikan model dan metrik dengan NumPy dari nol.

## Ringkasan Hasil

### Bagian A — Linear Regression (Ads_Data.csv)

- Persamaan regresi: y = 29.3864 + 9.0711 x BiayaIklan
- Interpretasi: Setiap kenaikan biaya iklan Rp1 juta, penjualan diperkirakan naik ~Rp9.07 juta
- R2 Training: 0.9618
- R2 Testing: 0.8464
- RMSE Testing: 9.3344 juta Rp

Eksperimen Learning Rate (Gradient Descent):

| Learning Rate | Hasil |
|---|---|
| 0.001 | Terlalu lambat, belum konvergen setelah 5000 iterasi |
| 0.02 | Konvergen, hasil hampir sama dengan normal equation |
| 0.1 | Divergen (loss overflow, parameter menjadi nan) |

Prediksi Penjualan:

| Biaya Iklan | Prediksi Penjualan |
|---|---|
| 4.5 juta | 70.21 juta |
| 7.0 juta | 92.88 juta |
| 12.0 juta | 138.24 juta (ekstrapolasi, kurang dapat dipercaya) |

### Bagian B — Logistic Regression (Email_Data.csv)

- Persamaan: P(Spam) = sigmoid(-11.191 + 1.026 x JumlahLink + 0.878 x KataPromo)
- Accuracy: 0.9333
- Precision: 1.0000
- Recall: 0.9000
- F1-Score: 0.9474

Confusion Matrix (Threshold 0.5):

| | Prediksi Bukan Spam | Prediksi Spam |
|---|---|---|
| Aktual Bukan Spam | 5 (TN) | 0 (FP) |
| Aktual Spam | 1 (FN) | 9 (TP) |

Eksperimen Threshold:

| Threshold | Precision | Recall |
|---|---|---|
| 0.3 | 1.0 | 0.9 |
| 0.5 | 1.0 | 0.9 |
| 0.7 | 1.0 | 0.9 |

Hasil sama karena tidak ada probabilitas data testing yang berada di antara 0.3 sampai 0.7.

### Bagian C — Pemahaman Konsep

Terjawab lengkap di notebook (C1 sampai C5), meliputi:

- Alasan Logistic Regression termasuk klasifikasi
- Perbandingan normal equation vs gradient descent
- Pentingnya data training vs testing dan overfitting
- Perbedaan MSE (regresi) dan Log Loss (klasifikasi)
- Faktor yang memengaruhi perbedaan hasil antar mahasiswa

### Bonus — Perbandingan dengan scikit-learn (+5)

| Model | Implementasi Sendiri | scikit-learn |
|---|---|---|
| Linear Regression (koefisien) | 29.3864 / 9.0711 | 29.3864 / 9.0711 |
| Logistic Regression (koefisien) | -11.1911 / 1.0264 / 0.8778 | -10.4979 / 0.9537 / 0.8242 |
| Accuracy Testing | 0.9333 | 0.9333 |

Analisis: Perbedaan koefisien Logistic Regression terjadi karena scikit-learn secara default menggunakan regularisasi L2, sedangkan implementasi gradient descent di notebook ini tidak memakai regularisasi.

## Teknologi

- Python 3
- NumPy — implementasi model & metrik dari nol
- pandas — manipulasi data
- matplotlib — visualisasi
- scikit-learn — hanya untuk soal bonus

## Deadline Pengumpulan

- Reg B: Jumat, 23 Oktober 2026, 23:59 WIB
- Reg C: Sabtu, 24 Oktober 2026, 23:59 WIB

---

Tugas ini dibuat untuk memenuhi UTS mata kuliah Machine Learning.
