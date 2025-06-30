# Recomendation-System_CC25

# Laporan Proyek Machine Learning - Nama Anda

## Project Overview
### Latar Belakang
Dalam era digital ini, volume informasi yang tersedia bagi individu telah tumbuh secara eksponensial. Ini seringkali menyebabkan masalah kelebihan informasi (information overload), di mana pengguna kesulitan menemukan konten yang relevan di antara jutaan pilihan yang ada. Di industri penerbitan, dengan jutaan judul buku yang dirilis setiap tahun, memilih buku yang sesuai dengan preferensi pribadi menjadi tantangan tersendiri bagi pembaca. Tanpa panduan, pembaca mungkin melewatkan buku-buku potensial yang sangat mereka sukai atau menghabiskan waktu mencari di antara pilihan yang tidak relevan.

Sistem rekomendasi muncul sebagai solusi krusial untuk mengatasi masalah ini dengan mempersonalisasi pengalaman pengguna. Sistem ini menganalisis preferensi dan perilaku pengguna di masa lalu (baik secara eksplisit melalui rating maupun implisit melalui interaksi) untuk menyarankan item baru yang kemungkinan besar akan disukai. Konsep ini telah berhasil diterapkan di berbagai platform besar seperti Netflix (film), Amazon (produk), dan Spotify (musik), membuktikan efektivitasnya dalam meningkatkan keterlibatan pengguna dan kepuasan pelanggan [1, 2].

Proyek ini bertujuan untuk membangun sistem rekomendasi buku menggunakan dataset Book-Crossing, yang berisi data rating buku dari komunitas pembaca online. Sistem ini diharapkan dapat membantu pengguna menemukan buku-buku baru yang relevan dengan selera mereka, sekaligus membantu penerbit dan penulis dalam menargetkan audiens yang tepat. Dengan menyediakan rekomendasi yang dipersonalisasi, proyek ini berupaya meningkatkan pengalaman membaca dan efisiensi penemuan buku bagi jutaan pembaca.

### Referensi
[1] Riccio, D., & Conte, D. (2020). Recommender Systems: A Survey of the State of the Art. ACM Computing Surveys (CSUR), 53(5), 1-38.

[2] Aggarwal, C. C. (2016). Recommender Systems: The Textbook. Springer.

## Business Understanding

Pada bagian ini, Anda perlu menjelaskan proses klarifikasi masalah.

Bagian laporan ini mencakup:

### Problem Statements
Proyek sistem rekomendasi buku ini berupaya menjawab beberapa masalah utama yang dihadapi oleh pembaca dan platform buku:
- Pernyataan Masalah 1: Kesulitan Pengguna Menemukan Buku yang Relevan. Dengan jutaan judul buku yang tersedia, pengguna seringkali kewalahan dan kesulitan dalam menyaring dan menemukan buku-buku yang benar-benar sesuai dengan minat dan preferensi mereka. Ini dapat menyebabkan kelelahan keputusan (decision fatigue) atau kehilangan minat dalam mencari buku baru.
- Pernyataan Masalah 2: Efisiensi Penemuan Buku Baru yang Rendah. Pembaca mungkin terjebak dalam membaca genre atau penulis yang sama secara berulang dan melewatkan potensi penemuan buku-buku menarik di luar lingkaran kebiasaan mereka. Proses penemuan buku baru secara manual seringkali memakan waktu dan tidak efisien.
- Pernyataan Masalah 3: Kurangnya Personalisasi Pengalaman Membaca. Platform buku dan toko buku online umumnya menawarkan daftar buku terlaris atau populer, tetapi kurang dalam memberikan rekomendasi yang spesifik untuk setiap individu berdasarkan riwayat dan preferensi unik mereka.

### Goals
Berdasarkan pernyataan masalah di atas, tujuan utama dari proyek sistem rekomendasi buku ini adalah:
- Jawaban pernyataan masalah 1 : Mengembangkan model yang mampu merekomendasikan buku yang sangat relevan kepada pengguna, sehingga meningkatkan kepuasan dan keterlibatan pembaca.
- Jawaban pernyataan masalah 2 : Menyediakan mekanisme otomatis untuk penemuan buku baru yang efisien, membantu pengguna menjelajahi berbagai judul di luar preferensi mereka yang sudah ada.
- Jawaban pernyataan masalah 3 : Menciptakan pengalaman membaca yang lebih personal dan menarik bagi setiap pengguna, dengan menyarankan buku berdasarkan riwayat interaksi dan preferensi yang teridentifikasi.

## Data Understanding
Data yang digunakan dalam proyek sistem rekomendasi buku ini adalah Book-Crossing Dataset, yang dapat diunduh dari Kaggle melalui tautan berikut: Book-Recommendation-Dataset by Arashnic. Dataset ini merupakan kumpulan data dari komunitas pembaca buku online BookCrossing.com dan terdiri dari tiga file CSV terpisah: Books.csv, Ratings.csv, dan Users.csv.

Secara total, dataset ini berisi:
- 271.360 entri buku unik dalam Books.csv.
- 278.858 entri pengguna unik dalam Users.csv.
- 445.839 entri rating dalam Ratings.csv.

Kondisi data awal menunjukkan adanya beberapa nilai yang hilang, tipe data yang tidak konsisten ('Year-Of-Publication' yang bisa berupa string), dan rating implisit (nilai 0) yang perlu ditangani. Data rating juga sangat sparse, artinya sebagian besar pengguna hanya memberi rating pada sebagian kecil dari total buku yang tersedia.

Berikut adalah uraian variabel-variabel pada setiap DataFrame:

1. Books.csv
    - ISBN: (Object) International Standard Book Number, pengidentifikasi unik untuk setiap buku. Ini adalah kunci penghubung dengan DataFrame Ratings.
    - Book-Title: (Object) Judul buku.
    - Book-Author: (Object) Nama penulis buku.
    - Year-Of-Publication: (Object/Integer) Tahun publikasi buku. Awalnya dapat berisi nilai non-numerik.
    - Publisher: (Object) Nama penerbit buku.
    - Image-URL-S: (Object) URL gambar sampul buku ukuran kecil.
    - Image-URL-M: (Object) URL gambar sampul buku ukuran sedang.
    - Image-URL-L: (Object) URL gambar sampul buku ukuran besar.

2. Users.csv

    - User-ID: (Integer) Pengidentifikasi unik untuk setiap pengguna. Ini adalah kunci penghubung dengan DataFrame Ratings.
    - Location: (Object) Lokasi geografis pengguna (negara, kota, dll.).
    - Age: (Object/Float) Usia pengguna. Awalnya dapat berisi nilai non-numerik atau NaN.

3. Ratings.csv

    - User-ID: (Integer) Pengidentifikasi pengguna yang memberikan rating.
    - ISBN: (Object) ISBN buku yang diberi rating.
    - Book-Rating: (Integer) Rating yang diberikan pengguna pada buku, berkisar dari 0 hingga 10. Rating 0 sering diartikan sebagai rating implisit (buku yang hanya dilihat/diakses).

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data beserta insight atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model sisten rekomendasi yang Anda buat untuk menyelesaikan permasalahan. Sajikan top-N recommendation sebagai output.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menyajikan dua solusi rekomendasi dengan algoritma yang berbeda.
- Menjelaskan kelebihan dan kekurangan dari solusi/pendekatan yang dipilih.

## Evaluation
Pada bagian ini Anda perlu menyebutkan metrik evaluasi yang digunakan. Kemudian, jelaskan hasil proyek berdasarkan metrik evaluasi tersebut.

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.
