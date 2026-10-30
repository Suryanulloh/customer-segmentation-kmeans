# Segmentasi Pelanggan Mal dengan K-Means

Proyek clustering untuk mengelompokkan pelanggan mal berdasarkan usia, pendapatan tahunan, dan spending score menggunakan K-Means. Dikerjakan secara berkelompok (Kelompok 11 Beginner, Modul 9) dalam program Junior Data Science di VINIX Seven Aurum (MSIB Batch 3).

## Tujuan
Menemukan segmen pelanggan yang berbeda supaya strategi pemasaran bisa disesuaikan untuk tiap segmen.

## Data
- Dataset Mall Customers (dataset publik, sumber: [isi tautan sumber]): 200 pelanggan dan 5 kolom (CustomerID, Gender, Age, Annual Income (k$), Spending Score (1-100)).
- Tidak ada nilai kosong. Gender (Female 112, Male 88) diubah ke numerik tetapi tidak dipakai dalam clustering.

## Metode
1. Pengecekan dan persiapan data (tipe data, missing value, encoding gender).
2. EDA: statistik deskriptif dan distribusi pendapatan serta spending score.
3. Standardisasi tiga fitur (usia, pendapatan, spending score) dengan StandardScaler.
4. Penentuan jumlah klaster dengan Elbow Method dan Silhouette Score.
5. K-Means dengan k = 5, lalu visualisasi 3D interaktif (Plotly) dan interpretasi profil tiap klaster.
6. Eksperimen tambahan: K-Means k = 2 hanya dengan pendapatan dan spending score, divisualisasikan dalam heatmap.

## Hasil
Silhouette Score untuk k = 5 sekitar 0,41-0,42, termasuk sedang. Score lebih tinggi sedikit pada k = 6 (0,428), tetapi k = 5 dipilih berdasarkan Elbow Method.

| Klaster | Rata-rata usia | Pendapatan (k$) | Spending score | Gambaran |
| --- | --- | --- | --- | --- |
| 0 | 55 | 48 | 42 | Pelanggan lebih tua, pendapatan dan belanja menengah |
| 1 | 33 | 86 | 82 | Pendapatan tinggi, belanja tinggi |
| 2 | 26 | 26 | 75 | Muda, pendapatan rendah, belanja tinggi |
| 3 | 27 | 54 | 41 | Muda, pendapatan dan belanja menengah |
| 4 | 44 | 90 | 18 | Pendapatan tinggi, belanja rendah |

Eksperimen k = 2 membagi pelanggan menjadi kelompok belanja tinggi (spending score rata-rata 76,7, usia 32) dan belanja rendah (33,98, usia 43).

## Rekomendasi (interpretasi)
- Klaster 1 adalah segmen paling menarik, cocok untuk program loyalitas dan produk premium.
- Klaster 4 berpendapatan tinggi tetapi jarang berbelanja, sehingga berpotensi diaktifkan lewat promosi yang dipersonalisasi.
- Klaster 2 berbelanja banyak meski berpendapatan rendah, cocok untuk promo dan diskon.

## Keterbatasan
- Dataset kecil (200 pelanggan) dan umum dipakai untuk latihan, jadi hasil belum mencerminkan kondisi nyata.
- Silhouette Score masih sedang, sehingga batas antar klaster tidak terlalu tegas.

## Teknologi
Python, Google Colab, pandas, NumPy, Matplotlib, Seaborn, scikit-learn, Plotly

## Cara menjalankan
1. Buka `customer_segmentation_kmeans.ipynb` di Google Colab.
2. Unggah `Mall_Customers.csv` saat diminta (sel `files.upload()`).
3. Jalankan sel secara berurutan.

## Tim
Kelompok 11 Beginner, VINIX Seven Aurum (MSIB Batch 3): Ilham Suryanulloh dan rekan satu kelompok.
