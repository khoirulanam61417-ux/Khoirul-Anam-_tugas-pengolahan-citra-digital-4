# Khoirul-Anam-_tugas-pengolahan-citra-digital-4
# Image Processing Task – Transformasi Grayscale dan Histogram

## Deskripsi

Project ini merupakan implementasi beberapa teknik dasar **pengolahan citra digital** menggunakan Python dan OpenCV pada Google Colab.
Proses yang dilakukan meliputi konversi warna, peningkatan kualitas citra, serta analisis histogram.

Teknik yang digunakan dalam project ini antara lain:

1. Konversi RGB ke Grayscale
2. Konversi Grayscale ke Biner
3. Konversi Grayscale ke m-bit
4. Pengaturan Brightness
5. Pengaturan Contrast
6. Histogram Grayscale
7. Histogram Equalization

---

# 1. Konversi RGB ke Grayscale

### Teori

Citra digital berwarna memiliki tiga komponen warna utama yaitu **Red (R), Green (G), dan Blue (B)**.
Untuk menyederhanakan proses pengolahan citra, gambar berwarna sering diubah menjadi **grayscale**.

Nilai grayscale dihitung menggunakan rumus:

Gray = 0.299R + 0.587G + 0.114B

Nilai pixel grayscale berada pada rentang **0–255**, dimana:

* 0 = hitam
* 255 = putih

### Implementasi

Pada kode Python, konversi dilakukan menggunakan fungsi OpenCV:

cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)

### Kesimpulan

Proses pada kode sama dengan teori, hanya saja perhitungannya dilakukan otomatis oleh library OpenCV.

---

# 2. Konversi Grayscale ke Biner

### Teori

Citra biner adalah citra yang hanya memiliki **dua nilai pixel**, yaitu:

* 0 (hitam)
* 255 (putih)

Proses konversi dilakukan menggunakan metode **thresholding**.

Rumus:

g(x,y) = 1 jika f(x,y) > T
g(x,y) = 0 jika f(x,y) ≤ T

T adalah nilai threshold.

### Implementasi

Kode menggunakan fungsi:

cv2.threshold()

Fungsi ini akan mengubah nilai pixel berdasarkan nilai threshold yang ditentukan.

---

# 3. Konversi Grayscale ke m-bit

### Teori

Citra grayscale normal memiliki **8 bit** sehingga memiliki **256 tingkat intensitas (0–255)**.

Pada konversi **m-bit**, jumlah tingkat intensitas dikurangi menjadi:

2^m

Contoh:

* 4 bit = 16 tingkat intensitas

Tujuan metode ini adalah untuk mengurangi kompleksitas data citra.

### Implementasi

Kode melakukan pengurangan jumlah level intensitas menggunakan operasi matematika pada pixel.

---

# 4. Pengaturan Brightness

### Teori

Brightness adalah proses untuk mengatur tingkat **kecerahan gambar**.

Rumus perubahan brightness:

f'(x,y) = f(x,y) + b

Dimana:

* f(x,y) = nilai pixel awal
* b = nilai penambah kecerahan

Jika b positif maka gambar menjadi lebih terang.

### Implementasi

Kode menggunakan fungsi:

cv2.convertScaleAbs()

Parameter **beta** digunakan untuk menambah brightness.

---

# 5. Pengaturan Contrast

### Teori

Contrast digunakan untuk meningkatkan perbedaan antara area terang dan gelap dalam citra.

Rumus:

f'(x,y) = a × f(x,y)

Dimana:

a = faktor kontras

Jika nilai a lebih besar dari 1 maka kontras gambar akan meningkat.

### Implementasi

Pada kode Python, kontras diatur menggunakan parameter **alpha** pada fungsi:

cv2.convertScaleAbs()

---

# 6. Histogram Grayscale

### Teori

Histogram adalah grafik yang menunjukkan **distribusi intensitas pixel pada suatu citra**.

Histogram grayscale memiliki nilai dari:

0 – 255

Histogram dapat digunakan untuk mengetahui karakteristik gambar, misalnya:

* Histogram di kiri → gambar gelap
* Histogram di kanan → gambar terang
* Histogram menumpuk → kontras rendah
* Histogram merata → kontras tinggi

### Implementasi

Histogram dibuat menggunakan fungsi matplotlib:

plt.hist()

---

# 7. Histogram Equalization

### Teori

Histogram Equalization adalah teknik **peningkatan kualitas citra (image enhancement)** yang bertujuan untuk meratakan distribusi intensitas pixel pada histogram.

Metode ini menggunakan **distribusi kumulatif (CDF)** untuk memetakan kembali nilai intensitas pixel sehingga kontras gambar meningkat.

### Implementasi

Kode Python menggunakan fungsi OpenCV:

cv2.equalizeHist()

Fungsi ini akan meratakan histogram sehingga detail gambar lebih terlihat.

---

# Perbandingan Teori dan Implementasi

Secara umum, teori yang dijelaskan di kelas dan implementasi pada kode Python memiliki prinsip yang sama.
Perbedaannya adalah pada kode Python, proses perhitungan dilakukan secara otomatis menggunakan library seperti **OpenCV** dan **NumPy**, sehingga proses pengolahan citra menjadi lebih cepat dan efisien.

---

# Referensi

1. Gonzalez, R. C., & Woods, R. E. (2018). Digital Image Processing. Pearson.
2. Pizer, S. M., et al. (1987). Adaptive Histogram Equalization and Its Variations.
3. Kusnadi, K., Riana, D., & Syahrani, M. (2022). Pengolahan Citra Digital dengan Metode Transformasi Grayscale dan Pemerataan Histogram.
4. 
