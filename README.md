# 📊 Statistik Pro+ v3.8 — Alternatif SPSS berbasis Streamlit

Statistik Pro+ v3.8 adalah aplikasi statistik interaktif berbasis Streamlit yang dirancang sebagai alternatif ringan dari SPSS untuk analisis data, penelitian kuantitatif, skripsi/tesis, survei, dan laporan statistik.

Versi ini menambahkan modul **Kompatibilitas Data** agar pengguna awam tidak hanya mendapat pesan error ketika data tidak cocok, tetapi juga mendapat diagnosis dan instruksi praktis: apa yang harus diubah, ditambahkan, diganti, atau dibersihkan sebelum analisis.

## ✨ Fitur Utama

### 1. Data View & Variable View
- Import data dari CSV, Excel, dan SPSS `.sav`
- Data editor interaktif
- Variable View ala SPSS:
  - nama variabel
  - label variabel
  - tipe data
  - measurement level: Nominal, Ordinal, Scale
  - role variabel
  - value labels, contoh: `1=Laki-laki; 2=Perempuan`
  - user-missing values, contoh: `99, 999`

### 2. Kompatibilitas Data & Panduan Perbaikan
- Skor kesiapan data 0–100
- Diagnosis data tidak kompatibel:
  - kolom kosong atau duplikat
  - kolom angka yang terbaca sebagai teks
  - missing value tinggi
  - kode missing seperti `-`, `NA`, `99`
  - variabel tanpa variasi
  - kategori terlalu banyak atau grup terlalu kecil
  - kolom ID yang sebaiknya tidak dipakai sebagai variabel analisis
  - mismatch antara tipe data dan measurement level
- Rekomendasi untuk pengguna awam:
  - apa yang sebaiknya diubah
  - apa yang sebaiknya ditambahkan
  - apa yang sebaiknya diganti/dihapus
  - langkah perbaikan yang bisa dilakukan di Transform/Variable View
- Profil setiap kolom
- Rekomendasi uji statistik yang cocok dengan dataset aktif
- Checklist khusus sebelum t-test, ANOVA, korelasi, regresi, reliabilitas, dan EFA
- Ekspor laporan kompatibilitas ke CSV dan Output Viewer

### 3. Transformasi Data
- Compute variable
- Recode into different variable
- Reverse coding item Likert
- Standardize / Z-score
- Filter / select cases
- Split file untuk workflow output
- Rename dan drop variables
- Syntax / audit trail sederhana

### 4. Statistik Deskriptif
- Mean, median, standar deviasi, min, max
- Skewness dan kurtosis
- Tabel frekuensi
- Explore by group
- Uji normalitas Shapiro-Wilk / D'Agostino

### 5. Uji Statistik
- One-Sample T-Test
- Independent T-Test, wide dan long format
- Paired T-Test
- One-Way ANOVA
- Two-Way ANOVA
- Tukey HSD post-hoc
- Korelasi Pearson, Spearman, Kendall
- Crosstab dan Chi-Square
- Mann-Whitney U
- Wilcoxon Signed-Rank
- Kruskal-Wallis + Dunn post-hoc jika dependency tersedia
- Friedman Test
- Uji asumsi: normalitas, Levene, outlier sederhana

### 6. Regresi
- Regresi linear berganda
- Regresi logistik biner
- Koefisien, CI, p-value, odds ratio
- VIF multikolinearitas
- Diagnostik residual:
  - Jarque-Bera
  - Durbin-Watson
  - Breusch-Pagan

### 7. Reliabilitas, PCA, dan Faktor
- Cronbach’s Alpha
- Corrected item-total correlation
- Alpha if item deleted
- PCA explained variance dan component loadings
- Exploratory Factor Analysis / EFA
- Engine EFA stabil tanpa ketergantungan penuh pada factor-analyzer
- Principal Axis Factoring fallback berbasis correlation matrix
- KMO dan Bartlett’s Test
- Factor loadings, communalities, eigenvalues, variance explained

### 8. Visualisasi
- Histogram
- Box plot
- Scatter plot + trendline OLS
- Bar chart
- Correlation heatmap
- Q-Q plot

### 9. Insight & Makna Riset
- Tab **Insight Riset** untuk mengubah output statistik menjadi narasi pembahasan
- Sintesis temuan utama dari output tersimpan
- Insight per output: makna statistik, effect size, kualitas instrumen, kelayakan faktor, dan saran pelaporan
- Template narasi pembahasan yang bisa diunduh sebagai Markdown
- Penyimpanan sintesis insight ke Output Viewer

### 10. Output Viewer & Ekspor
- Output analisis tersimpan seperti Output Viewer sederhana
- Interpretasi otomatis berbasis p-value/effect/model summary
- Ekspor:
  - CSV
  - Excel data + output
  - Markdown report
  - HTML report
  - Word `.docx`
  - Syntax log `.sps`

## 🚀 Cara Menjalankan

```bash
pip install -r requirements.txt
streamlit run app.py
```

## 📁 File dalam paket

```text
statistik_pro_spss_v3_8/
├── app.py
├── requirements.txt
├── README.md
└── sample_data.csv
```

## 🧪 Data Contoh

Aplikasi menyertakan `sample_data.csv` dan tombol **Data Contoh** di sidebar. Data contoh berisi variabel kelompok, gender, kecemasan, motivasi, nilai akhir, status lulus, dan item kuesioner Likert.

## Alur yang Disarankan untuk Pengguna Awam

1. Upload data atau gunakan Data Contoh.
2. Buka **Kompatibilitas Data**.
3. Ikuti daftar prioritas: perbaiki yang **Kritis** dan **Tinggi** dulu.
4. Cek **Variable View** agar Measure/Role sesuai.
5. Jalankan statistik deskriptif.
6. Pilih uji statistik yang direkomendasikan aplikasi.
7. Setelah output keluar, buka **Insight Riset** untuk membaca maknanya.
8. Ekspor output ke Excel/Word/HTML/Markdown.

## ⚠️ Catatan Metodologis

Aplikasi ini membantu mempercepat analisis statistik, tetapi interpretasi akhir tetap perlu mempertimbangkan desain penelitian, kualitas data, ukuran sampel, skala pengukuran, dan asumsi statistik yang relevan.

Untuk laporan akademik, sebaiknya selalu laporkan statistik uji, derajat kebebasan, p-value, confidence interval, effect size, dan hasil uji asumsi.

---

Developed by Galuh Adi Insani · Enhanced as Statistik Pro+ v3.8 · Compatibility & Beginner Guidance Workflow
