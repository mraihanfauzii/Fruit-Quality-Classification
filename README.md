# Fruit and Vegetable Quality Classification

**Deskripsi** Sistem klasifikasi gambar untuk mendeteksi kualitas buah (Healthy vs Rotten) pada 4 jenis buah (Banana, Mango, Potato, Strawberry) dengan menggunakan CNN berbasis transfer learning (MobileNetV2).

Dataset yang digunakan adalah Dataset Fruit and Vegetable Disease (Healthy vs Rotten) yang berisi 14 jenis buah-buahan yang mana masing-masingnya memiliki 2 class yaitu baik atau busuk, dengan total class yaitu sebanyak 28 dengan total semua gambar berjumlah 29,291.
https://www.kaggle.com/datasets/muhammad0subhan/fruit-and-vegetable-disease-healthy-vs-rotten 

Karena dataset merupakan gabungan dari gambar yang telah diaugmentasi dan yang belum oleh pemilik dataset dan karena kebetulan gambar yang di augmentasi dinamakan sesuai dengan augmentasinya juga, maka pada data cleaning akan dibuat kode untuk menghapus gambar augmentasi dari dataset, karena pada proyek ini akan dilakukan augmentasi sendiri jadi akan digunakan gambar yang belum diaugmentasi.

Untuk jumlah class yang digunakan yaitu sebanyak 8 class saja jadi total 4 buah yaitu Banana, Mango, Potato, Strawberry yang mana masing-masing terbagi menjadi 2 class yaitu baik dan busuk jadi total ada 8 class, total gambar yang akan digunakan dari dataset berjumlah 10,256.

Proyek ini dibuat dengan tujuan membuat sistem klasifikasi gambar untuk mendeteksi apakah suatu buah itu masih layak konsumsi atau sudah tidak layak yaitu sudah busuk.

## 🎯 Kriteria Proyek

| No | Kriteria/Saran                                                  | Status            | Penjelasan Singkat                                                                                                                                              |
| -- | --------------------------------------------------------- | ----------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1  | Dataset ≥ 10.000 gambar                                   | ✅ Tercapai        | Dataset awal 29.291 gambar, setelah cleaning tersisa 10.256 gambar.                                                                                             |
| 2  | Split menjadi Train/Validation/Test (X/Y/Z)               | ✅ Tercapai        | Split 70%/15%/15% (7.179/1.538/1.539).                                                                                                                          |
| 3  | Model menggunakan Sequential, Conv2D, Pooling layer       | ✅ Tercapai        | Transfer learning MobileNetV2 (frozen) + Conv2D + MaxPooling + Flatten + Dense.                                                                                 |
| 4  | Akurasi ≥ 95% pada Train dan Test                         | ✅ Tercapai        | Train Accuracy: 99.08%, Test Accuracy: 97.98%.                                                                                                                  |
| 5  | Plot akurasi dan loss model                               | ✅ Tercapai        | Visualisasi perubahan `accuracy` dan `loss` selama training dan validasi.                                                                                       |
| 6  | Menyimpan model: SavedModel, TF‑Lite, TFJS                | ✅ Tercapai        | Model berhasil diekspor ke SavedModel, TFLite, dan TFJS.                                                                                                    |
| 7  | Mengimplementasikan Callback                              | ✅ Tercapai        | EarlyStopping & ModelCheckpoint pada `val_accuracy`.                                                                                                            |
| 8  | Dataset asli resolusi tidak seragam (tanpa preprocessing) | ✅ Tercapai        | Dataset asli mix resolusi; preprocessing (resize & augmentasi) baru dilakukan oleh `ImageDataGenerator`.                                                        |
| 9  | Memiliki minimal 3 kelas                                  | ✅ Tercapai        | Digunakan 8 kelas (4 buah × 2 kondisi).                                                                                                                         |
| 10 | Melakukan inference menggunakan SavedModel/TF‑Lite/TFJS   | ✅ Tercapai        | Inference dilakukan menggunakan TF-Lite.                                                                                                                              |
| 11 | Struktur direktori pengumpulan: sesuai gambar 1           | ✅ Tercapai        | Struktur folder `submission/` sudah sesuai.                                                                                                                     |

---

## 📁 Struktur Direktori `submission/`

```
submission/
├── tfjs_model/
│   ├── group1-shard1of3.bin
│   ├── group1-shard2of3.bin
│   ├── group1-shard3of3.bin
│   └── model.json
├── tflite/
│   ├── model.tflite
│   └── label.txt
├── saved_model/
│   ├── saved_model.pb
│   ├── fingerprint.pb
│   └── variables/
│       ├── variables.data-00000-of-00001
│       └── variables.index
├── notebook.ipynb
├── README.md
└── requirements.txt
```
