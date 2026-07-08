# CONTINUE_PROMPT.md

Salin prompt berikut ke ChatGPT baru setelah mengupload ZIP proyek ini.

---

Saya mengupload ZIP proyek **Statistik Pro+**. Tolong lanjutkan pengembangan dari versi terbaru di ZIP ini, **jangan mulai ulang dari nol**.

Langkah pertama:

1. Baca `CHATGPT_MEMORY.md`.
2. Baca `README.md`.
3. Baca `requirements.txt`.
4. Inspect `app.py` sebelum mengubah apa pun.

Konteks penting:

- Aplikasi ini adalah Streamlit statistics suite yang ingin menjadi alternatif SPSS/alat hitung statistika.
- UI harus ramah user awam dan tidak membingungkan.
- Pertahankan Mode Pemula/Mode Ahli dan Level Detail Ringkas/Lengkap.
- Jangan membuat tab Streamlit bertumpuk yang merender semua fitur sekaligus; gunakan navigasi stabil dan render menu aktif saja.
- Semua output statistik harus dimaknai, bukan hanya angka.
- Jika data tidak kompatibel, aplikasi harus memberi saran apa yang harus diubah, ditambah, diganti, dibersihkan, atau dihapus.
- Hindari error Streamlit seperti duplicate key dan slider dengan `min_value == max_value`.

Jika melakukan perubahan:

- Buat versi ZIP baru.
- Update README.
- Update `CHATGPT_MEMORY.md` jika perubahan besar.
- Jalankan:

```bash
python -m py_compile app.py
zip -T <nama_zip_baru>.zip
```

Target pengembangan berikutnya yang disarankan:

1. Project Save/Load `.statpro.zip`.
2. Report Builder Word/PDF yang lebih rapi.
3. Guided Analysis Wizard end-to-end.
4. Runtime stabilization untuk Streamlit Cloud.
5. Validasi akurasi dengan output pembanding SPSS/R/JASP.
