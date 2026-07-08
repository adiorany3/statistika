# Statistik Pro+ v4.1 — Comprehensive Guided Statistics Suite

Aplikasi statistik berbasis Streamlit yang dirancang sebagai alternatif alat hitung/statistika bergaya SPSS, tetapi tetap ramah untuk user awam.

## Prinsip v4.1

- **Lengkap, tetapi tidak membingungkan**: fitur teknis tersedia, namun dibuka bertahap lewat mode Pemula/Ahli.
- **Dipandu dari data sampai laporan**: upload data → cek kompatibilitas → rekomendasi uji → analisis → insight riset → ekspor laporan.
- **Aman untuk pemula**: aplikasi memberi tahu apa yang perlu diubah, ditambahkan, diganti, atau diperbaiki bila data belum kompatibel.
- **Cukup detail untuk user ahli**: tersedia transformasi data, uji statistik, regresi, reliabilitas, EFA/PAF, visualisasi, output viewer, dan syntax log.

## Fitur Utama

### UI & Workflow

- Mode **Pemula** dan **Ahli**
- Level detail **Ringkas** dan **Lengkap**
- Halaman **Mulai Cepat** dengan skor kesiapan data dan langkah berikutnya
- Navigasi stabil berbasis menu, bukan tab bertumpuk
- Panduan lengkap dipisahkan di menu **Panduan** agar UI utama tetap bersih

### Data & Compatibility

- Import CSV, Excel, dan SPSS `.sav`
- Data View dan Variable View
- Value labels dan user-missing values
- Compatibility score 0–100
- Profil kolom dan saran peran variabel
- Data Repair Assistant:
  - rapikan nama kolom
  - ubah kode missing umum menjadi NaN
  - konversi angka yang terbaca sebagai teks
  - rapikan spasi kategori
  - hapus kolom kosong/konstan
  - imputasi sederhana median/modus
  - winsorize outlier ekstrem 3×IQR

### Smart Statistical Assistant

- Wizard pemilihan uji otomatis
- Research Design Planner
- Sample Size & Power Calculator
- Kalkulator statistik manual
- Kalkulator distribusi dan nilai kritis
- Effect Size & Assumption guide
- Template narasi BAB 4, APA Style, dan ringkasan manajerial

### Analisis Statistik

- Deskriptif dan frekuensi
- Normalitas, crosstab, chi-square
- One-sample t-test
- Independent t-test
- Paired t-test
- One-way ANOVA, Two-way ANOVA
- Tukey HSD dan post-hoc nonparametrik
- Mann-Whitney, Wilcoxon, Kruskal-Wallis, Friedman
- Korelasi Pearson/Spearman/Kendall
- Regresi linear dan logistik
- VIF, residual diagnostics, Durbin-Watson, Breusch-Pagan
- Cronbach's Alpha
- PCA
- EFA/Principal Axis Factoring fallback stabil
- KMO dan Bartlett

### Reporting

- Insight riset otomatis
- Output Viewer ala SPSS
- Ekspor Excel, Markdown, HTML, Word `.docx`
- Syntax/audit trail `.sps`
- Template narasi untuk laporan penelitian

## Cara Menjalankan

```bash
pip install -r requirements.txt
streamlit run app.py
```

## Rekomendasi Penggunaan

1. Mulai dari **Mode Pemula**.
2. Upload data atau gunakan data contoh.
3. Buka **🚀 Mulai Cepat**.
4. Perbaiki masalah di **Kompatibilitas Data** atau **Data Repair Assistant**.
5. Pilih uji lewat **Smart Assistant**.
6. Jalankan analisis.
7. Maknai hasil melalui **Insight Riset**.
8. Ekspor laporan melalui **Output & Ekspor**.

## Catatan Metodologis

Aplikasi ini membantu analisis dan pelaporan, tetapi interpretasi akhir tetap perlu disesuaikan dengan desain penelitian, teori, kualitas instrumen, dan konteks data. Untuk keputusan riset formal, sertakan effect size, confidence interval, asumsi, dan keterbatasan, bukan hanya p-value.


## Update v4.1

- Memperbaiki error di halaman 🚀 Mulai Cepat: `AttributeError: str object has no attribute get`.
- Diagnosis kompatibilitas data kini dinormalisasi otomatis baik berbentuk DataFrame, dict, list, maupun teks.
- Rekomendasi langkah berikutnya dibuat lebih defensif agar UI tetap berjalan meskipun format issue berubah.
