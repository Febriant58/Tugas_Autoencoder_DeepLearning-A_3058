# 🎨 Image Colorization with Autoencoders

Proyek ini mengimplementasikan autoencoder sederhana untuk tugas pewarnaan citra (image colorization), di mana input berupa citra grayscale dan output berupa citra berwarna. Proyek ini merupakan bagian dari tugas mata kuliah *Deep Learning*.

## 📂 Dataset

Dataset yang digunakan berasal dari Kaggle:  🔗 [aayush9753/image-colorization-dataset]

  - Total gambar: **11.478**
  - Digunakan: subset dengan **minimal 20 pasang** citra
  - Format: 
    - Input: Gambar grayscale
    - Output: Gambar berwarna

Citra diproses dalam format LAB untuk memisahkan komponen luminance dan chrominance, yang sangat cocok untuk pewarnaan.

## 🧠 Arsitektur Autoencoder

Model dibangun menggunakan TensorFlow dan Keras dengan struktur encoder-decoder:

**Encoder:**
- Conv2D + ReLU
- Downsampling (melalui stride)


**Decoder:**
- UpSampling2D
- Conv2D + Sigmoid (output layer)

Arsitektur ini memungkinkan model mempelajari representasi fitur dari gambar grayscale dan merekonstruksi kembali warna dari fitur tersebut.

## ⚙️ Spesifikasi Pelatihan / Performa
Model menggunakan fungsi loss Mean Squared Error (MSE) dan optimizer Adam. Selama pelatihan, nilai loss menurun secara konsisten, menunjukkan proses pembelajaran berjalan baik.
  ### 📉 Grafik Loss Selama Training
![download](https://github.com/user-attachments/assets/ee53912b-c414-4cc9-9800-42e78f12065a)

## 🖼️ Hasil Prediksi

Berikut adalah beberapa contoh citra grayscale dan hasil colorization menggunakan autoencoder:
![download](https://github.com/user-attachments/assets/82b28d7f-80f4-4929-8a2a-2c714a768026)

## 🧾 Catatan

- Model dapat dikembangkan lebih lanjut dengan menambah jumlah data, arsitektur lebih kompleks, atau pretraining.
- Seluruh implementasi terdapat di file `Image_colorization_with_Autoencoders.ipynb`




