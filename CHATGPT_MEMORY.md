# CHATGPT_MEMORY.md — Statistik Pro+ v4.6

File ini dibuat agar proyek dapat dilanjutkan di sesi ChatGPT lain tanpa kehilangan konteks. Jika Anda membuka proyek ini di chat baru, upload ZIP ini lalu minta ChatGPT membaca `CHATGPT_MEMORY.md` terlebih dahulu.

---

## 1. Identitas Proyek

**Nama aplikasi:** Statistik Pro+  
**Versi saat ini:** v4.6 — Memory Continuity Edition  
**Basis teknis:** Python + Streamlit  
**Tujuan utama:** Menjadi alternatif alat hitung statistika/SPSS yang mudah digunakan oleh user awam, tetapi tetap cukup detail untuk mahasiswa, peneliti, dosen, dan analis data.

Aplikasi ini dikembangkan bertahap dari aplikasi awal yang hanya memiliki T-Test dan ANOVA dasar, lalu diperluas menjadi suite statistik terpandu dengan mode pemula/ahli, kompatibilitas data, insight riset, reliabilitas, PCA/EFA, kalkulator statistik, dan template laporan.

---

## 2. File Penting dalam ZIP

| File | Fungsi |
|---|---|
| `app.py` | Aplikasi utama Streamlit |
| `requirements.txt` | Dependency Python |
| `sample_data.csv` | Data contoh untuk uji coba cepat |
| `README.md` | Panduan menjalankan aplikasi |
| `CHATGPT_MEMORY.md` | Konteks penuh proyek untuk dilanjutkan di chat/sesi lain |
| `CONTINUE_PROMPT.md` | Prompt siap salin untuk ChatGPT baru |
| `project_memory.json` | Ringkasan terstruktur untuk mesin/AI |

---

## 3. Cara Melanjutkan di ChatGPT Baru

Di chat baru, gunakan instruksi seperti ini:

> Saya mengupload ZIP proyek Statistik Pro+. Tolong baca `CHATGPT_MEMORY.md`, `README.md`, `requirements.txt`, dan `app.py`. Lanjutkan pengembangan dari versi terbaru. Jangan mulai ulang dari nol. Pertahankan UI agar tidak membingungkan user awam.

Lalu upload ZIP ini.

---

## 4. Prinsip Desain UI yang Harus Dipertahankan

1. **UI tidak boleh membingungkan user awam.**
2. Gunakan **Mode Pemula** dan **Mode Ahli**.
3. Gunakan **Level Detail: Ringkas / Lengkap**.
4. Hindari tab Streamlit bertumpuk yang berat dan rawan konflik.
5. Prefer navigasi stabil berbasis `radio`, `selectbox`, atau segmented menu.
6. Detail lanjutan ditempatkan dalam `st.expander()`.
7. Setiap hasil statistik harus disertai:
   - arti angka,
   - keputusan,
   - makna riset,
   - saran tindakan berikutnya,
   - contoh narasi laporan jika memungkinkan.
8. Jangan hanya menampilkan p-value; sertakan effect size, confidence interval, asumsi, dan rekomendasi lanjutan.
9. Jika data tidak kompatibel, aplikasi harus memberi tahu apa yang perlu diubah/ditambahkan/diganti/dihapus, bukan hanya error.
10. Bagian utama harus tetap sederhana; bagian ahli boleh detail.

---

## 5. Fitur yang Sudah Ada per v4.5/v4.6

### A. Input dan Data Management

- Upload CSV, Excel, dan SPSS `.sav` jika dependency tersedia.
- Input manual/data contoh.
- Data View.
- Variable View ala SPSS.
- Metadata variabel:
  - label,
  - measurement level: nominal/ordinal/scale,
  - value labels,
  - user-missing values.
- Pengolahan missing value berbasis metadata.

### B. Kompatibilitas Data

- Skor kesiapan data.
- Diagnosis masalah data.
- Prioritas masalah: kritis/tinggi/sedang/ringan/info.
- Profil kolom.
- Rekomendasi uji yang cocok.
- Rekomendasi apa yang harus:
  - diubah,
  - ditambahkan,
  - diganti,
  - dibersihkan,
  - dihapus.

### C. Mulai Cepat

- Ringkasan status data.
- Rekomendasi langkah berikutnya.
- Saran peran variabel.
- Tabel rekomendasi analisis.
- Peta fitur aplikasi.

Catatan teknis: fungsi terkait termasuk `render_quick_start`, `_issues_to_records`, `build_next_best_actions`, `suggest_analysis_table`, `variable_role_suggestions`, `analysis_decision_matrix`, dan `comprehensive_ui_feature_map`.

### D. Smart Assistant

- Wizard pemilihan uji statistik otomatis.
- Research design planner.
- Data Repair Assistant.
- Sample size & power calculator.
- Kalkulator statistik manual.
- Effect size & asumsi.
- Template narasi laporan.

### E. Transformasi dan Repair Data

- Rapikan nama kolom.
- Konversi angka yang terbaca sebagai teks.
- Ubah kode missing seperti `-`, `NA`, `?`, `null` menjadi missing value.
- Hapus kolom kosong total.
- Hapus kolom tanpa variasi.
- Rapikan spasi kategori.
- Imputasi sederhana median/modus.
- Winsorize outlier ekstrem 3×IQR.

### F. Statistik Deskriptif dan Normalitas

- Deskriptif numerik.
- Frekuensi kategori.
- Skewness dan kurtosis.
- Interpretasi otomatis skewness/kurtosis.
- Uji normalitas.
- Rekomendasi tindakan jika normalitas tidak terpenuhi.

Jika normalitas tidak terpenuhi, aplikasi harus menyarankan:

| Tujuan analisis | Alternatif/saran |
|---|---|
| 2 kelompok independen | Mann-Whitney U atau Welch t-test |
| Pre-post/berpasangan | Wilcoxon Signed-Rank |
| 3+ kelompok | Kruskal-Wallis + Dunn post-hoc |
| Korelasi | Spearman atau Kendall |
| Regresi | Cek residual, robust SE, transformasi, bootstrap |
| Data sangat menceng | Transformasi log/sqrt/Box-Cox/Yeo-Johnson |
| Banyak outlier | Cek input, winsorize dengan alasan, robust analysis |

### G. Uji Statistik

- One-sample t-test.
- Independent t-test.
- Paired t-test.
- One-way ANOVA.
- ANOVA format wide/long.
- Tukey post-hoc.
- Korelasi.
- Chi-square.
- Nonparametrik seperti Mann-Whitney, Wilcoxon, Kruskal-Wallis, Friedman, dan Dunn post-hoc jika dependency tersedia.

### H. Regresi

- Regresi linear/multiple regression.
- Logistic regression jika data memungkinkan.
- VIF/multikolinearitas.
- Diagnostic checks seperti Durbin-Watson, Jarque-Bera, Breusch-Pagan jika library tersedia.

### I. Reliabilitas, PCA, dan EFA

- Cronbach’s Alpha.
- Item-total statistics.
- Interpretasi reliabilitas otomatis.
- PCA.
- Interpretasi PCA otomatis.
- EFA/factor analysis.
- Interpretasi EFA otomatis.
- KMO dan Bartlett.
- Communalities.
- Factor loadings.
- Eigenvalues.
- Variance explained.

Catatan penting EFA:

- Default engine EFA adalah fallback stabil berbasis Principal Axis Factoring agar tahan konflik `factor-analyzer` vs `scikit-learn`.
- `factor-analyzer` boleh tetap ada, tetapi fallback harus tetap tersedia.
- Jangan membuat slider dengan `min_value == max_value`; Streamlit akan crash.
- Jika hanya 2 variabel EFA, jumlah faktor valid hanya 1. Gunakan nilai tetap/penjelasan, bukan slider.

### J. Visualisasi

- Histogram.
- Boxplot.
- Scatter.
- Bar chart.
- Q-Q plot.
- Correlation heatmap.
- Visualisasi lain sesuai kebutuhan.

### K. Insight Riset

- Membaca output analisis tersimpan.
- Memberikan:
  - temuan utama,
  - makna statistik,
  - makna substantif,
  - kekuatan bukti,
  - catatan asumsi,
  - kualitas instrumen,
  - saran pelaporan,
  - rekomendasi analisis lanjutan.

### L. Output Viewer dan Export

- Output hasil analisis disimpan dalam session.
- Export ke Excel.
- Export Markdown.
- Export HTML.
- Export Word `.docx`.
- Syntax/audit trail `.sps`.

---

## 6. Bug yang Pernah Terjadi dan Sudah Diperbaiki

### 6.1 PCA Slider Crash

Error:

```text
Slider min_value must be less than the max_value. The values were 1 and 1.
```

Penyebab: PCA hanya punya 1 variabel/komponen, tetapi widget slider dibuat dari 1 ke 1.

Solusi: tampilkan slider hanya jika `max_value > min_value`; jika tidak, gunakan nilai tetap dan tampilkan info.

### 6.2 Export Markdown Butuh `tabulate`

Error:

```text
ImportError: Missing optional dependency 'tabulate'
```

Solusi:

- Tambahkan `tabulate` ke `requirements.txt`.
- Buat fallback Markdown renderer manual agar tidak crash.

### 6.3 EFA `force_all_finite` vs `ensure_all_finite`

Error:

```text
check_array() got an unexpected keyword argument 'force_all_finite'
```

Penyebab: konflik `factor-analyzer` dengan `scikit-learn` baru.

Solusi:

- Patch kompatibilitas.
- Tambahkan fallback EFA stabil tanpa ketergantungan penuh pada `factor-analyzer`.
- Default EFA diarahkan ke fallback stabil.

### 6.4 Tab Tidak Berfungsi / UI Berat

Penyebab: banyak tab Streamlit kompleks dirender bersamaan dan bisa memicu konflik/berat.

Solusi:

- Hindari tab bertumpuk.
- Gunakan navigasi radio/selectbox.
- Render hanya menu aktif.
- Tangani error lokal agar satu menu tidak menjatuhkan seluruh aplikasi.

### 6.5 Duplicate Element Key

Error:

```text
StreamlitDuplicateElementKey
```

Penyebab: auto-key widget untuk sidebar/container membaca label dengan keliru.

Solusi:

- Perbaiki generator key.
- Pastikan widget penting memakai key eksplisit.
- Hindari key sama di sidebar dan main area.

### 6.6 Mulai Cepat: `'str' object has no attribute 'get'`

Penyebab: diagnosis kompatibilitas masuk dalam bentuk string/list/DataFrame, tetapi fungsi mengharapkan dict.

Solusi:

- Tambahkan `_issues_to_records()` untuk normalisasi input issues.

### 6.7 Mulai Cepat: `suggest_analysis_table` Undefined

Penyebab: fungsi terpanggil tetapi belum ikut masuk final.

Solusi:

- Tambahkan `suggest_analysis_table()` resmi dan fallback.

### 6.8 EFA Jumlah Faktor Slider Crash

Error:

```text
Slider min_value must be less than the max_value. The values were 1 and 1.
```

Penyebab: EFA hanya memungkinkan 1 faktor.

Solusi:

- Slider jumlah faktor hanya muncul jika `max_factors >= 2`.
- Jika `max_factors == 1`, gunakan `n_factors = 1` otomatis dan tampilkan info.

---

## 7. Aturan Teknis untuk Pengembangan Berikutnya

1. Selalu tes sintaks:

```bash
python -m py_compile app.py
```

2. Selalu tes ZIP:

```bash
zip -T nama_file.zip
```

3. Jangan memakai slider jika min dan max sama.

Contoh aman:

```python
if max_value > min_value:
    value = st.slider("Label", min_value, max_value, default)
else:
    value = min_value
    st.info("Hanya ada satu pilihan yang valid.")
```

4. Semua widget di fitur baru harus punya `key` eksplisit atau memakai mekanisme auto-key yang stabil.

5. Semua fungsi yang dipanggil dari UI harus didefinisikan sebelum dipanggil.

6. Jangan memecah fitur besar ke tab yang semuanya dirender bersamaan. Gunakan menu aktif.

7. Error per fitur harus ditangani lokal:

```python
try:
    render_feature()
except Exception as e:
    st.error("Bagian ini mengalami kendala, tetapi aplikasi tetap berjalan.")
    st.exception(e)
```

8. Fitur untuk user awam harus memakai bahasa non-teknis terlebih dahulu, lalu detail statistik diletakkan di expander.

9. Saat menambahkan analisis statistik, sertakan:

- definisi tujuan,
- syarat data,
- asumsi,
- output angka,
- interpretasi,
- effect size bila relevan,
- confidence interval bila memungkinkan,
- apa yang dilakukan jika asumsi gagal,
- narasi laporan.

10. Pertahankan kompatibilitas Python modern dan Streamlit Cloud.

---

## 8. Dependency Saat Ini

`requirements.txt` saat ini berisi:

```text
streamlit>=1.36.0
pandas>=2.0.0
numpy>=1.24.0
scipy>=1.10.0
openpyxl>=3.1.0
xlsxwriter>=3.1.0
plotly>=5.18.0
statsmodels>=0.14.0
scikit-learn>=1.6.0,<1.8.0
pyreadstat>=1.2.7
python-docx>=1.1.0
tabulate>=0.9.0
scikit-posthocs>=0.9.0
factor-analyzer>=0.5.1
pingouin>=0.5.4
```

Catatan:

- Jika Streamlit Cloud memakai Python sangat baru dan dependency gagal, pertimbangkan membuat `runtime.txt` untuk pin versi Python, misalnya `python-3.11` atau `python-3.12`.
- `factor-analyzer` rawan konflik dengan versi `scikit-learn`, jadi fallback EFA harus tetap dipertahankan.

---

## 9. Rekomendasi Pengembangan Berikutnya

### Prioritas tertinggi

1. **Runtime/Deployment Stabilization**
   - Tambahkan `runtime.txt` untuk Streamlit Cloud.
   - Tambahkan smoke test sederhana.
   - Tambahkan `requirements-lock.txt` jika ingin versi sangat stabil.

2. **Project Save/Load**
   - Simpan dataset + metadata + output + syntax + insight ke `.statpro.zip`.
   - Load kembali proyek di sesi lain.

3. **Report Builder Final**
   - User bisa memilih output mana yang masuk laporan.
   - Export Word/PDF lebih rapi.
   - Ada template BAB 4, artikel, dan laporan manajerial.

4. **Guided Analysis Wizard End-to-End**
   - Pilih tujuan riset.
   - Pilih variabel.
   - Cek kompatibilitas.
   - Jalankan uji.
   - Interpretasi.
   - Buat narasi.

5. **Test Accuracy Validation**
   - Tambahkan data kecil dengan hasil pembanding dari SPSS/R/JASP.
   - Buat tabel validasi hasil.

### Prioritas lanjutan

- ANCOVA.
- MANOVA.
- Repeated Measures ANOVA lengkap.
- Mixed model/multilevel analysis.
- ROC curve.
- Cluster analysis.
- Discriminant analysis.
- Survival analysis.
- Time series dasar.
- Bootstrapping.
- Robust regression.
- McDonald’s Omega.
- CFA sederhana atau integrasi semopy jika stabil.

---

## 10. Arahan Jika ChatGPT Lain Melanjutkan

Saat melanjutkan proyek ini:

1. Mulai dari ZIP versi terbaru ini, bukan versi lama.
2. Baca `CHATGPT_MEMORY.md` dan `README.md` lebih dahulu.
3. Jangan menghapus fitur yang sudah ada tanpa alasan.
4. Jangan membuat UI semakin ramai.
5. Tambahkan fitur baru dalam mode terpandu dan expander.
6. Setiap perubahan harus diakhiri dengan ZIP baru.
7. Cantumkan versi baru pada README dan memory file jika ada perubahan besar.
8. Jalankan minimal:

```bash
python -m py_compile app.py
zip -T statistik_pro_spss_vX_Y.zip
```

9. Jika user melaporkan error, patch langsung dari traceback dan pertahankan backward compatibility.
10. Bila menambahkan output statistik, selalu tambahkan interpretasi ramah user awam.

---

## 11. Status Terakhir

Versi terakhir sebelum file memory dibuat adalah **v4.5**. Versi ini menjadi **v4.6** karena menambahkan file continuity/memory, tanpa mengubah logika utama aplikasi.

Perubahan v4.6:

- Menambahkan `CHATGPT_MEMORY.md`.
- Menambahkan `CONTINUE_PROMPT.md`.
- Menambahkan `project_memory.json`.
- Memperbarui README agar menjelaskan cara melanjutkan proyek di sesi ChatGPT lain.

Aplikasi utama tetap sama seperti v4.5, yaitu versi yang sudah memperbaiki bug slider EFA jumlah faktor.


---

## Update v5.0 — Research Analytics Suite

Versi ini menambahkan menu **🔬 Analisis Lanjutan** agar aplikasi semakin dekat dengan alternatif alat hitung statistika/SPSS. Fitur yang ditambahkan:

1. Bootstrapping & Effect Size: bootstrap mean, selisih mean, korelasi, koefisien regresi, Cohen’s d, Hedges’ g, Cohen’s dz, Cramer’s V.
2. ANCOVA, MANOVA, dan Repeated Measures ANOVA dasar.
3. Mediasi sederhana dengan bootstrap indirect effect dan moderasi sederhana dengan interaction term.
4. Forecasting sederhana: moving average, exponential smoothing, dan trend linear.
5. Missing Value Analysis dan Custom Tables: pola missing, crosstab, chi-square, Cramer’s V, ringkasan by group.
6. Validasi & Benchmark: checklist reproducibility, package status, dan saran benchmark terhadap SPSS/R/JASP.
7. Ditambahkan `runtime.txt` berisi `python-3.11` untuk mengurangi masalah package di Streamlit Cloud yang memakai Python terlalu baru.

Prinsip penting v5.0:
- Jangan gunakan tab bertumpuk untuk fitur besar.
- Semua widget baru harus punya `key` eksplisit.
- Hindari slider jika nilai minimum dan maksimum bisa sama.
- Bungkus renderer fitur besar dengan `try/except` lokal.
- Untuk fitur advanced, lebih baik tampilkan pesan ramah + saran perbaikan daripada crash.
