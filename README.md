# FaceFit Barber Data Science

Repo ini berisi analisis data, eksplorasi, dan model pendukung untuk aplikasi FaceFit Barber.

## Struktur Repository

- `data/`
  - `dataset_before_balancing/` - dataset awal sebelum penyeimbangan kelas.
  - `dataset_after_balancing/` - dataset yang sudah diseimbangkan untuk training dan evaluasi.
- `notebooks/`
  - `Business_Understanding.ipynb` - pemahaman bisnis dan tujuan proyek.
  - `FaceFit_DS_M2_Fixed.ipynb` - notebook analisis lanjutan dan perbaikan model.
  - `FaceFit_DS_W3_EDA.ipynb` - eksplorasi data awal (EDA).
  - `FaceFit_W1.ipynb` - notebook awal untuk pendahuluan data science.
- `src/`
  - `dashboard.py` - skrip untuk dashboard atau visualisasi hasil.
- `requirements.txt` - daftar paket Python yang dibutuhkan.
- `LICENSE` - lisensi proyek.

## Tujuan

Tujuan repo ini adalah mendukung aplikasi utama FaceFit Barber dengan:

- eksplorasi bentuk wajah dan gaya rambut,
- persiapan dataset untuk model AI,
- eksperimen dan dokumentasi model data science,
- referensi untuk pipeline analisis data dan visualisasi.

## Cara Menjalankan

1. Siapkan environment Python, misalnya dengan `venv`:
   ```bash
   python -m venv venv
   .\venv\Scripts\activate
   ```
2. Install dependensi:
   ```bash
   pip install -r requirements.txt
   ```
3. Jalankan notebook menggunakan Jupyter:
   ```bash
   pip install notebook
   jupyter notebook
   ```
4. Atau jalankan dashboard:
   ```bash
   python src\dashboard.py
   ```

## Catatan

- Pastikan data di `data/` sudah tersedia sebelum menjalankan analisis.
- Notebook menyimpan alur kerja analisis dan hasil eksperimen model.

## Kontribusi

Jika kamu ingin menambah model, notebook, atau pipeline data baru, buat branch baru dan ajukan pull request.

## Lisensi

Lisensi sama dengan repo utama.
