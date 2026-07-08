# Statistik Pro+ v4.6 — Memory Continuity Edition

Aplikasi Streamlit untuk analisis statistik yang dirancang sebagai alternatif alat hitung statistika/SPSS dengan UI terpandu untuk pengguna awam dan fitur detail untuk pengguna ahli.


## Pembaruan v4.6

Versi ini menambahkan file continuity/memory agar proyek dapat dilanjutkan di sesi ChatGPT lain tanpa kehilangan konteks.

### File continuity yang ditambahkan

- `CHATGPT_MEMORY.md` — konteks lengkap proyek, fitur, bug yang pernah diperbaiki, prinsip UI, dan arah pengembangan berikutnya.
- `CONTINUE_PROMPT.md` — prompt siap salin untuk membuka proyek ini di ChatGPT/session lain.
- `project_memory.json` — ringkasan terstruktur untuk AI/tooling.

Jika ingin melanjutkan di chat baru, upload ZIP ini lalu minta ChatGPT membaca `CHATGPT_MEMORY.md` terlebih dahulu.

## Pembaruan v4.5

Versi ini memperbaiki bug pada bagian **Reliabilitas & Faktor → EFA** ketika pengguna hanya memilih 2 variabel. Pada kondisi tersebut jumlah faktor maksimum yang valid hanya 1, sedangkan widget slider Streamlit tidak mengizinkan `min_value` sama dengan `max_value`.

### Perbaikan utama

- Slider **Jumlah faktor** pada EFA hanya muncul jika jumlah faktor maksimum minimal 2.
- Jika hanya 2 variabel EFA dipilih, aplikasi otomatis menetapkan **1 faktor** dan menampilkan penjelasan yang ramah user.
- Ditambahkan safety clamp sebelum perhitungan EFA agar jumlah faktor tidak melebihi batas valid berdasarkan jumlah variabel dan jumlah baris data lengkap.
- Aplikasi tetap menjaga interpretasi otomatis Reliabilitas, PCA, dan EFA dari versi sebelumnya.

## Fitur utama aplikasi

- Mode Pemula dan Mode Ahli.
- Mulai Cepat dengan skor kesiapan data dan rekomendasi langkah.
- Data View & Variable View ala SPSS.
- Kompatibilitas data dan rekomendasi perbaikan.
- Smart Assistant untuk rekomendasi uji otomatis.
- Transformasi dan Data Repair Assistant.
- Statistik deskriptif, frekuensi, skewness, kurtosis, dan normalitas.
- Rekomendasi tindakan jika normalitas tidak terpenuhi.
- T-test, ANOVA, korelasi, chi-square, dan uji nonparametrik.
- Regresi dan diagnostic checks.
- Reliabilitas, PCA, EFA/faktor, dan interpretasi riset otomatis.
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

## Catatan EFA

- Untuk EFA, minimal pilih 2 variabel numerik.
- Jika hanya 2 variabel dipilih, aplikasi hanya dapat mengekstraksi 1 faktor.
- Jika ingin memilih lebih dari 1 faktor, gunakan minimal 3 variabel numerik.
- Default engine EFA adalah fallback stabil berbasis Principal Axis Factoring agar lebih tahan terhadap konflik versi `factor-analyzer` dan `scikit-learn`.
