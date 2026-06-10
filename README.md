# TUGAS-BESAR-ANALISIS-BIG-DATA-KELOMPOK-26
Tugas Besar Mata Kuliah Analisis Big Data 2026 kelompok 26 Program Studi Sains Data Institut Teknologi Sumatera

# Analisis Big Data SDG 8 Menggunakan Apache Spark dan Arsitektur Medallion

## Deskripsi Proyek

Proyek ini merupakan implementasi analisis big data pada **Sustainable Development Goals (SDG) Goal 8: Decent Work and Economic Growth** menggunakan **Apache Spark**, **PySpark**, dan **Arsitektur Medallion**.

Tujuan utama proyek adalah membangun pipeline data yang terstruktur untuk mengolah data SDG berskala global, menganalisis hubungan antara **produktivitas tenaga kerja** dan **pertumbuhan ekonomi**, serta membandingkan performa pemrosesan data menggunakan **Apache Spark** dan **Pandas**.

Dataset yang digunakan berasal dari **United Nations Statistics Division (UNSD)** dan mencakup berbagai indikator SDG Goal 8 dari banyak negara dalam rentang waktu yang panjang.

---

## Tujuan Proyek

* Mengimplementasikan Arsitektur Medallion (Bronze, Silver, Gold) menggunakan Apache Spark.
* Melakukan proses ETL (Extract, Transform, Load) terhadap data SDG Goal 8.
* Menganalisis tren pertumbuhan ekonomi global.
* Mengidentifikasi hubungan antara produktivitas tenaga kerja dan pertumbuhan ekonomi.
* Membandingkan performa Apache Spark dengan Pandas pada proses analisis data.

---

## Arsitektur Medallion

Pipeline data dibangun menggunakan pendekatan **Medallion Architecture** yang terdiri dari tiga lapisan utama:

### Bronze Layer

Menyimpan data mentah hasil ingest dari sumber asli tanpa modifikasi sehingga integritas data tetap terjaga.

### Silver Layer

Melakukan proses pembersihan dan transformasi data, meliputi:

* Penanganan missing values
* Normalisasi atribut
* Konversi tipe data
* Penghapusan data duplikat
* Validasi kualitas data

### Gold Layer

Menyediakan data siap analisis melalui:

* Agregasi statistik
* Analisis tren ekonomi
* Perbandingan antarnegara
* Analisis korelasi
* Visualisasi hasil

---

## 🛠️ Teknologi yang Digunakan

| Teknologi        | Fungsi                        |
| ---------------- | ----------------------------- |
| Python           | Bahasa pemrograman utama      |
| Apache Spark     | Pemrosesan data terdistribusi |
| PySpark          | API Python untuk Spark        |
| Pandas           | Baseline pemrosesan data      |
| Parquet          | Format penyimpanan data       |
| Matplotlib       | Visualisasi data              |
| Jupyter Notebook | Lingkungan pengembangan       |

---

## Struktur Proyek

```text
├── data/
│   ├── raw/
│   ├── bronze/
│   ├── silver/
│   └── gold/
│
├── notebooks/
│   ├── bronze_layer.ipynb
│   ├── silver_layer.ipynb
│   └── gold_layer.ipynb
│
├── results/
│   ├── visualizations/
│   ├── tables/
│   └── reports/
│
├── README.md
└── requirements.txt
```

---

## Hasil Analisis

### Tren Pertumbuhan Ekonomi Global

Hasil analisis menunjukkan bahwa pertumbuhan ekonomi dunia mengalami fluktuasi sepanjang periode pengamatan.

Beberapa temuan penting:

* Pertumbuhan ekonomi global sempat mencapai lebih dari **15%** pada awal tahun 2000-an.
* Krisis keuangan global tahun **2008** menyebabkan kontraksi ekonomi yang signifikan.
* Pandemi **COVID-19 pada tahun 2020** menghasilkan penurunan terdalam hingga sekitar **-6%**.
* Setelah pandemi, ekonomi global kembali pulih dan stabil pada kisaran **2%** pada periode 2022–2024.

---

### Perbandingan Pertumbuhan Antarnegara

Berdasarkan hasil agregasi Gold Layer:

| Negara      | Rata-rata Pertumbuhan |
| ----------- | --------------------- |
| Albania     | ~4,7%                 |
| Afghanistan | >2%                   |
| Algeria     | ~1,4%                 |
| Andorra     | <1%                   |

Albania menunjukkan performa pertumbuhan ekonomi tertinggi dibandingkan negara lain pada sampel hasil visualisasi.

---

### Korelasi Produktivitas dan Pertumbuhan Ekonomi

Analisis menggunakan **Pearson Correlation** menghasilkan:

```text
r = 0.8248
```

Interpretasi:

* Hubungan positif sangat kuat.
* Peningkatan produktivitas tenaga kerja cenderung diikuti peningkatan pertumbuhan ekonomi.
* Produktivitas tenaga kerja menjadi salah satu faktor penting dalam mendukung pertumbuhan ekonomi berkelanjutan.

---

## Evaluasi Performa

Perbandingan dilakukan terhadap dataset yang terdiri dari **255.761 baris data**.

| Metrik         | Pandas               | Apache Spark         |
| -------------- | -------------------- | -------------------- |
| Total Baris    | 255.761              | 255.761              |
| Waktu Eksekusi | 46,73 detik          | 77,83 detik          |
| Throughput     | 5.473,75 baris/detik | 3.286,27 baris/detik |

### Temuan

Untuk ukuran dataset yang digunakan pada penelitian ini:

1. Pandas memberikan waktu eksekusi yang lebih cepat.

2. Throughput Pandas lebih tinggi dibandingkan Spark.

3. Apache Spark tetap unggul dari sisi skalabilitas dan lebih siap digunakan pada volume data yang jauh lebih besar.

---

## Kesimpulan

Implementasi Arsitektur Medallion berhasil mendukung proses pengolahan data SDG Goal 8 secara terstruktur mulai dari data mentah hingga analisis akhir.

Hasil penelitian menunjukkan adanya hubungan positif yang sangat kuat antara produktivitas tenaga kerja dan pertumbuhan ekonomi dengan nilai korelasi sebesar **0,8248**.

Pada lingkungan lokal dan ukuran data yang digunakan, **Pandas memberikan performa lebih baik dibandingkan Apache Spark**. Namun, Apache Spark tetap menjadi solusi yang lebih fleksibel untuk pengolahan data berskala besar karena mendukung komputasi terdistribusi dan skalabilitas yang tinggi.

---

## Tim Pengembang

| Nama                   | NIM       |
| ---------------------- | --------- |
| Eigi Arthamevia        | 123450011 |
| Natasya Amavisca       | 123450024 |
| Abdillah Fikri Al Pome | 123450062 |
| Arienta Khusnul Ananda | 123450097 |
