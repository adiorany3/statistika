# Prompt untuk melanjutkan proyek di ChatGPT lain

Saya mengunggah ZIP **Statistik Pro+ v5.2 — Research Analytics Suite**. Tolong baca file berikut terlebih dahulu:

1. `CHATGPT_MEMORY.md`
2. `README.md`
3. `project_memory.json`
4. `requirements.txt`
5. `app.py`

Lanjutkan dari versi terbaru ini, jangan mulai ulang dari nol.

Prinsip wajib:
- UI tidak boleh membingungkan user awam.
- Pertahankan Mode Pemula dan Mode Ahli.
- Jangan memakai tab Streamlit bertumpuk untuk fitur besar; gunakan menu aktif/radio.
- Semua widget baru wajib punya key eksplisit.
- Jangan membuat slider jika `min_value == max_value`.
- Setiap hasil statistik harus punya interpretasi dan saran tindakan.
- Cek `python -m py_compile app.py` dan `zip -T` sebelum memberi ZIP final.

Versi terbaru sudah memiliki menu **🔬 Analisis Lanjutan** dengan bootstrapping, effect size, ANCOVA, MANOVA, repeated measures ANOVA, mediasi, moderasi, forecasting sederhana, missing value analysis, custom tables, dan validasi/benchmark.


Catatan v5.2: sidebar footer sudah dihapus; jangan mengembalikannya kecuali diminta. Fitur unequal N sudah ditambahkan pada independent t-test dan one-way ANOVA dengan Welch/Games-Howell.
