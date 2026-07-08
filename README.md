# Statistik Pro+ v4.3 — Comprehensive Guided Statistics Suite

Aplikasi Streamlit untuk analisis statistik yang dirancang sebagai alternatif alat hitung statistika/SPSS dengan UI terpandu untuk pengguna awam dan fitur detail untuk pengguna ahli.

## Pembaruan v4.3

Versi ini menambahkan interpretasi distribusi dan panduan keputusan ketika normalitas tidak terpenuhi.

### Fitur baru

- **Interpretasi otomatis Skewness & Kurtosis** pada menu Deskriptif.
  - Menjelaskan apakah distribusi simetris, menceng kanan/kiri, datar, runcing, atau berpotensi memiliki outlier.
  - Menambahkan kolom **Saran Distribusi** agar user tahu langkah berikutnya.

- **Uji Normalitas + Rekomendasi Tindakan**.
  - Output normalitas sekarang tidak hanya menampilkan p-value, tetapi juga keputusan dan tindakan praktis.
  - Jika normalitas tidak tercapai, aplikasi menyarankan langkah seperti cek outlier, transformasi, uji nonparametrik, bootstrap, atau metode robust.

- **Panduan Normalitas & Distribusi**.
  - Ditambahkan pada menu **Smart Assistant → Effect Size & Asumsi**.
  - Ditambahkan juga pada menu **Panduan**.
  - Berisi tabel patokan skewness/kurtosis dan tabel tindakan ketika normalitas gagal.

- **Panduan untuk user awam**.
  - Penjelasan dibuat dalam bahasa praktis: apa masalahnya, kenapa penting, dan tindakan yang disarankan.
  - Cocok untuk membantu menyusun keputusan analisis dan narasi metodologi penelitian.

## Fitur utama aplikasi

- Data View & Variable View ala SPSS.
- Kompatibilitas data dan rekomendasi perbaikan.
- Smart Assistant untuk rekomendasi uji otomatis.
- Transformasi dan data repair assistant.
- Statistik deskriptif, frekuensi, normalitas.
- T-test, ANOVA, korelasi, chi-square, nonparametrik.
- Regresi dan diagnostic checks.
- Reliabilitas, PCA, EFA/faktor.
- Visualisasi.
- Insight riset dan template narasi laporan.
- Output viewer dan export laporan.

## Cara menjalankan

```bash
pip install -r requirements.txt
streamlit run app.py
```

## Catatan penggunaan

Jika menggunakan Streamlit Cloud, setelah mengganti file aplikasi sebaiknya lakukan:

```text
Manage app → Reboot app
```

Agar cache versi lama tidak digunakan.
