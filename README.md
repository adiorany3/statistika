# 📊 Statistik Pro+ v3.9 — Smart Statistical Assistant

Statistik Pro+ v3.9 adalah aplikasi statistik interaktif berbasis Streamlit yang dirancang sebagai alternatif ringan dari SPSS/JASP untuk analisis data, alat hitung statistika, penelitian kuantitatif, skripsi/tesis, survei, dan laporan statistik.

Versi ini menambahkan modul **Smart Statistical Assistant** agar pengguna awam tidak hanya melihat angka statistik, tetapi juga dipandu memilih uji yang tepat, memperbaiki data yang tidak cocok, menghitung kebutuhan sampel, memakai kalkulator statistik manual, dan menyusun narasi laporan penelitian.

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

### 3. Smart Statistical Assistant v3.9
Menu baru untuk menjadikan aplikasi lebih ramah sebagai **alat hitung statistika**:

- **Wizard Uji Otomatis**
  - user memilih tujuan riset
  - memilih variabel Y, X, dan grup
  - aplikasi memberi rekomendasi uji utama
  - aplikasi memberi alternatif jika asumsi tidak terpenuhi
  - aplikasi memberi checklist sebelum analisis
  - aplikasi menghitung effect size cepat bila memungkinkan

- **Data Repair Assistant**
  - rapikan nama kolom otomatis
  - ubah kode missing umum menjadi NaN
  - konversi kolom angka yang masih terbaca sebagai teks
  - hapus kolom kosong total
  - hapus kolom tanpa variasi

- **Sample Size & Power Calculator**
  - independent t-test
  - one-sample t-test
  - paired t-test
  - one-way ANOVA
  - korelasi
  - regresi berganda berbasis aturan praktis
  - survei proporsi / margin of error

- **Kalkulator Statistik Manual**
  - mean, median, modus
  - varians, standar deviasi, standard error
  - kuartil, IQR, min, max
  - confidence interval mean
  - z-score, t-score, persentil
  - distribusi Normal/Z, t, F, Chi-square, Binomial, dan Poisson

- **Template Narasi Laporan**
  - template BAB 4 skripsi/tesis
  - template APA style
  - template ringkasan manajerial
  - bisa disimpan ke Output Viewer dan diunduh sebagai Markdown

### 4. Transformasi Data
- Compute variable
- Recode into different variable
- Reverse coding item Likert
- Standardize / Z-score
- Filter / select cases
- Split file untuk workflow output
- Rename dan drop variables
- Syntax / audit trail sederhana

### 5. Statistik Deskriptif
- Mean, median, standar deviasi, min, max
- Skewness dan kurtosis
- Tabel frekuensi
- Explore by group
- Uji normalitas Shapiro-Wilk / D'Agostino

### 6. Uji Statistik
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

### 7. Regresi
- Regresi linear berganda
- Regresi logistik biner
- Koefisien, CI, p-value, odds ratio
- VIF multikolinearitas
- Diagnostik residual:
  - Jarque-Bera
  - Durbin-Watson
  - Breusch-Pagan

### 8. Reliabilitas, PCA, dan Faktor
- Cronbach’s Alpha
- Corrected item-total correlation
- Alpha if item deleted
- PCA explained variance dan component loadings
- Exploratory Factor Analysis / EFA
- Engine EFA stabil tanpa ketergantungan penuh pada factor-analyzer
- Principal Axis Factoring fallback berbasis correlation matrix
- KMO dan Bartlett’s Test
- Factor loadings, communalities, eigenvalues, variance explained

### 9. Visualisasi
- Histogram
- Box plot
- Scatter plot + trendline OLS
- Bar chart
- Correlation heatmap
- Q-Q plot

### 10. Insight & Makna Riset
- Tab **Insight Riset** untuk mengubah output statistik menjadi narasi pembahasan
- Sintesis temuan utama dari output tersimpan
- Insight per output: makna statistik, effect size, kualitas instrumen, kelayakan faktor, dan saran pelaporan
- Template narasi pembahasan yang bisa diunduh sebagai Markdown
- Penyimpanan sintesis insight ke Output Viewer

### 11. Output Viewer & Ekspor
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
statistik_pro_spss_v3_9/
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
3. Jika ada masalah, buka **Smart Assistant → Data Repair Assistant**.
4. Buka **Smart Assistant → Wizard Uji Otomatis** untuk memilih tujuan riset dan variabel.
5. Gunakan **Sample Size & Power** bila sedang menyusun proposal atau mengevaluasi kecukupan sampel.
6. Jalankan statistik deskriptif dan uji statistik yang direkomendasikan.
7. Setelah output keluar, buka **Insight Riset** untuk membaca maknanya.
8. Gunakan **Template Narasi Laporan** untuk menyusun BAB 4, APA style, atau ringkasan manajerial.
9. Ekspor output ke Excel/Word/HTML/Markdown.

## ⚠️ Catatan Metodologis

Aplikasi ini membantu mempercepat analisis statistik, tetapi interpretasi akhir tetap perlu mempertimbangkan desain penelitian, kualitas data, ukuran sampel, skala pengukuran, dan asumsi statistik yang relevan.

Untuk laporan akademik, sebaiknya selalu laporkan statistik uji, derajat kebebasan, p-value, confidence interval, effect size, dan hasil uji asumsi.

---

Developed by Galuh Adi Insani · Enhanced as Statistik Pro+ v3.9 · Smart Statistical Assistant Workflow
