# Klasifikasi Gambar — Intel Image Classification

> Tugas / proyek akhir Dicoding — Belajar Pengembangan Machine Learning
Model CNN untuk mengklasifikasikan gambar pemandangan alam ke dalam 6 kelas: buildings, forest, glacier, mountain, sea, street.

## Tech stack
- Python
- TensorFlow / Keras
- TensorFlow.js
- Scikit-learn
- Pandas, NumPy, Matplotlib, Seaborn
- Pillow, split-folders

## Dataset
[Intel Image Classification](https://www.kaggle.com/datasets/puneet6060/intel-image-classification) (Kaggle), berisi gambar pemandangan alam dalam 6 kelas: buildings, forest, glacier, mountain, sea, street. Data dibagi 80% train / 10% validation / 10% test.

## Alur proyek
1. **Setup & download dataset** — lewat Kaggle API
2. **Eksplorasi data** — cek jumlah gambar per kelas dan variasi resolusi
3. **Data splitting & preprocessing** — split ke train/val/test, dataset master tetap utuh
4. **Membangun model** — CNN Sequential dengan blok Conv2D + MaxPooling2D berulang, diakhiri Flatten, Dense, dan Dropout
5. **Custom callback** — training berhenti otomatis saat `accuracy >= 0.96` dan `val_accuracy >= 0.96` tercapai bersamaan, untuk mencegah overfitting
6. **Training model**
7. **Plot akurasi & loss**
8. **Evaluasi pada test set**
9. **Inferensi gambar baru**
10. **Konversi & export model** — ke SavedModel, TF-Lite, dan TFJS

## Hasil
- Test Accuracy: 0.8748
- Test Loss: 0.3629

## Struktur model
Sequential CNN: 4 blok Conv2D + MaxPooling2D, Flatten, Dropout, Dense.

## Struktur proyek
```
notebook.ipynb       # Notebook lengkap: eksplorasi, training, evaluasi, export
requirements.txt     # Dependencies
saved_model/          # Model format SavedModel
tflite/
  model.tflite         # Model format TensorFlow Lite
  label.txt             # Daftar label kelas
tfjs_model/            # Model format TensorFlow.js
```

## Format export
- **SavedModel** — `saved_model/`
- **TensorFlow Lite** — `tflite/model.tflite` + `tflite/label.txt`
- **TensorFlow.js** — `tfjs_model/`

## Instalasi
Clone repo:
```bash
git clone https://github.com/farhanlab/BFDL2_final-project-dicoding.git
cd BFDL2_final-project-dicoding
```

Install dependencies:
```bash
pip install -r requirements.txt
```

Jalankan `notebook.ipynb` di Jupyter Notebook atau Google Colab secara berurutan dari atas ke bawah. Diperlukan file `kaggle.json` (API token dari akun Kaggle) untuk mengunduh dataset — **jangan commit file ini ke repo**.

## Penulis
Muhammad Farhan Nurkhaeri
