# 📊 Statistik Pro+ v3.6 — Alternatif SPSS berbasis Streamlit

Statistik Pro+ v3.6 adalah aplikasi statistik interaktif berbasis Streamlit yang dirancang sebagai alternatif ringan dari SPSS untuk kebutuhan analisis data, penelitian kuantitatif, skripsi/tesis, survei, dan laporan statistik.

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

### 2. Transformasi Data
- Compute variable
- Recode into different variable
- Reverse coding item Likert
- Standardize / Z-score
- Filter / select cases
- Split file untuk workflow output
- Rename dan drop variables
- Syntax / audit trail sederhana

### 3. Statistik Deskriptif
- Mean, median, standar deviasi, min, max
- Skewness dan kurtosis
- Tabel frekuensi
- Explore by group
- Uji normalitas Shapiro-Wilk / D'Agostino

### 4. Uji Statistik
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

### 5. Regresi
- Regresi linear berganda
- Regresi logistik biner
- Koefisien, CI, p-value, odds ratio
- VIF multikolinearitas
- Diagnostik residual:
  - Jarque-Bera
  - Durbin-Watson
  - Breusch-Pagan

### 6. Reliabilitas, PCA, dan Faktor
- Cronbach’s Alpha
- Corrected item-total correlation
- Alpha if item deleted
- PCA explained variance dan component loadings
- Exploratory Factor Analysis / EFA
- Engine EFA stabil tanpa ketergantungan penuh pada factor-analyzer
- Principal Axis Factoring fallback berbasis correlation matrix
- KMO dan Bartlett’s Test
- Factor loadings, communalities, eigenvalues, variance explained

### 7. Visualisasi
- Histogram
- Box plot
- Scatter plot + trendline OLS
- Bar chart
- Correlation heatmap
- Q-Q plot

### 8. Insight & Makna Riset
- Tab **Insight Riset** untuk mengubah output statistik menjadi narasi pembahasan
- Sintesis temuan utama dari output tersimpan
- Insight per output: makna statistik, effect size, kualitas instrumen, kelayakan faktor, dan saran pelaporan
- Template narasi pembahasan yang bisa diunduh sebagai Markdown
- Penyimpanan sintesis insight ke Output Viewer

### 9. Output Viewer & Ekspor
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
statistik_pro_spss_v3_6/
├── app.py
├── requirements.txt
├── README.md
├── sample_data.csv
└── .streamlit/
    └── config.toml
```

## 🧪 Data Contoh

Aplikasi menyertakan `sample_data.csv` dan juga tombol **Data Contoh** di sidebar. Data contoh berisi variabel kelompok, gender, kecemasan, motivasi, nilai akhir, status lulus, dan item kuesioner Likert.

## ⚠️ Catatan Metodologis

Aplikasi ini membantu mempercepat analisis statistik, tetapi interpretasi akhir tetap perlu mempertimbangkan desain penelitian, kualitas data, ukuran sampel, skala pengukuran, dan asumsi statistik yang relevan.

Untuk laporan akademik, sebaiknya selalu laporkan statistik uji, derajat kebebasan, p-value, confidence interval, effect size, dan hasil uji asumsi.

---

Developed by Galuh Adi Insani · Enhanced as Statistik Pro+ v3.6


## Catatan Versi 3.2

- Memperbaiki kompatibilitas EFA pada scikit-learn versi terbaru yang mengganti parameter `force_all_finite` menjadi `ensure_all_finite`.
- EFA sekarang dipatch otomatis dari dalam aplikasi, sehingga tidak perlu downgrade scikit-learn.


## Catatan v3.4

- EFA kini memiliki **engine fallback stabil** tanpa `factor-analyzer`.
- Jika terjadi konflik `force_all_finite` / `ensure_all_finite` pada scikit-learn terbaru, pilih menu **Engine EFA → Fallback stabil tanpa factor-analyzer**.
- Aplikasi tetap mencoba `factor-analyzer` terlebih dahulu pada mode otomatis, lalu berpindah ke fallback bila dependency bermasalah.


## Catatan v3.6

- Menambahkan modul **Insight & Makna Riset**.
- Aplikasi kini tidak hanya menampilkan angka statistik, tetapi juga membantu menyusun makna riset: temuan utama, hasil non-signifikan, asumsi, kualitas pengukuran, dan rekomendasi analisis lanjutan.
- Insight dapat disimpan ke Output Viewer dan diekspor bersama laporan.
