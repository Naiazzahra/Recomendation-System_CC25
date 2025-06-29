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

**Rubrik/Kriteria Tambahan (Opsional)**:
- Jelaskan mengapa dan bagaimana masalah tersebut harus diselesaikan
- Menyertakan hasil riset terkait atau referensi. Referensi yang diberikan harus berasal dari sumber yang kredibel dan author yang jelas.
- Format Referensi dapat mengacu pada penulisan sitasi [IEEE](https://journals.ieeeauthorcenter.ieee.org/wp-content/uploads/sites/7/IEEE_Reference_Guide.pdf), [APA](https://www.mendeley.com/guides/apa-citation-guide/) atau secara umum seperti [di sini](https://penerbitdeepublish.com/menulis-buku-membuat-sitasi-dengan-mudah/)
- Sumber yang bisa digunakan [Scholar](https://scholar.google.com/)

## Business Understanding

Pada bagian ini, Anda perlu menjelaskan proses klarifikasi masalah.

Bagian laporan ini mencakup:

### Problem Statements

Menjelaskan pernyataan masalah:
- Pernyataan Masalah 1
- Pernyataan Masalah 2
- Pernyataan Masalah n

### Goals

Menjelaskan tujuan proyek yang menjawab pernyataan masalah:
- Jawaban pernyataan masalah 1
- Jawaban pernyataan masalah 2
- Jawaban pernyataan masalah n

Semua poin di atas harus diuraikan dengan jelas. Anda bebas menuliskan berapa pernyataan masalah dan juga goals yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menambahkan bagian “Solution Approach” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut: 

    ### Solution statements
    - Mengajukan 2 atau lebih solution approach (algoritma atau pendekatan sistem rekomendasi).

## Data Understanding
Paragraf awal bagian ini menjelaskan informasi mengenai jumlah data, kondisi data, dan informasi mengenai data yang digunakan. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

Selanjutnya, uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

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
