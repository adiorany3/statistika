# Statistik Pro+ v5.1 — Research Analytics Suite

Aplikasi Streamlit untuk analisis statistik yang dirancang sebagai alternatif alat hitung statistika/SPSS untuk riset dasar hingga menengah-lanjutan. Versi ini menambahkan fitur advanced, tetapi UI tetap dibuat sederhana melalui **Mode Pemula/Ahli**, navigasi radio, dan detail yang disimpan dalam expander.

## Pembaruan utama v5.0

### 🔬 Analisis Lanjutan
Menu baru **🔬 Analisis Lanjutan** berisi fitur SPSS-like yang sering dibutuhkan dalam riset:

- **Bootstrapping & Effect Size**
  - Bootstrap mean
  - Bootstrap selisih dua rata-rata
  - Bootstrap korelasi
  - Bootstrap koefisien regresi
  - Cohen’s d, Hedges’ g, Cohen’s dz, Cramer’s V

- **ANCOVA / MANOVA / Repeated Measures ANOVA**
  - ANCOVA dengan Type II/III sum of squares
  - Partial eta squared
  - MANOVA dasar
  - Repeated Measures ANOVA untuk data format long

- **Mediasi & Moderasi**
  - Mediasi sederhana X → M → Y
  - Bootstrap indirect effect
  - Moderasi sederhana dengan interaction term

- **Forecasting sederhana**
  - Moving average
  - Exponential smoothing
  - Trend linear

- **Missing Value Analysis & Custom Tables**
  - Ringkasan missing value
  - Pola missing value
  - Custom crosstab dengan persentase
  - Chi-square dan Cramer’s V
  - Tabel ringkasan numerik by group

- **Validasi & Benchmark**
  - Checklist reproduksibilitas
  - Status package dan output
  - Saran benchmark manual terhadap SPSS/R/JASP

## Prinsip anti-bug v5.0

- Tidak memakai tab Streamlit bertumpuk untuk fitur besar.
- Menu aktif saja yang dirender.
- Semua widget baru memakai key eksplisit.
- Slider berisiko diganti radio/number input defensif.
- Tidak membuat slider ketika `min_value == max_value`.
- Fitur advanced dibungkus `try/except` lokal agar error satu modul tidak menjatuhkan aplikasi.
- Ditambahkan `runtime.txt` untuk Streamlit Cloud agar memakai Python stabil.

## Fitur utama dari versi sebelumnya

- Mode Pemula dan Mode Ahli.
- Mulai Cepat dengan skor kesiapan data.
- Data View dan Variable View ala SPSS.
- Kompatibilitas data dan Data Repair Assistant.
- Smart Assistant untuk rekomendasi uji otomatis.
- Sample size dan power calculator.
- Statistik deskriptif, skewness, kurtosis, dan normalitas.
- Rekomendasi tindakan jika normalitas tidak terpenuhi.
- T-test, ANOVA, korelasi, chi-square, dan nonparametrik.
- Regresi dan diagnostic checks.
- Reliabilitas, PCA, EFA/faktor, dan interpretasi riset otomatis.
- Insight riset dan template narasi laporan.
- Output Viewer dan export Excel/Markdown/HTML/Word.
- File memory untuk melanjutkan proyek di sesi ChatGPT lain.

## Cara menjalankan lokal

```bash
pip install -r requirements.txt
streamlit run app.py
```

## Streamlit Cloud

Disarankan memakai Python stabil melalui file `runtime.txt`:

```text
python-3.11
```

Setelah upload versi baru:

```text
Manage app → Reboot app
```

## Catatan batasan

Aplikasi ini makin mendekati alternatif SPSS, tetapi belum menggantikan penuh modul enterprise SPSS seperti Complex Samples penuh, Exact Tests lengkap, SEM visual setara AMOS, GLMM/GEE lengkap, ARIMA advanced, dan validasi komersial IBM. Untuk riset formal, hasil penting tetap disarankan dibenchmark terhadap SPSS/R/JASP pada beberapa kasus uji.


## Update v5.1 — Persistent Footer Edition

- Footer `Developed by Galuh Adi Insani` dibuat lebih permanen dengan fixed bottom bar.
- Ditambahkan footer cadangan di sidebar.
- Padding bawah konten ditambah agar bagian akhir halaman tidak tertutup footer.
- Footer dirender sejak awal script sehingga tetap muncul walau menu tertentu mengalami error lokal.
