# Gerombol-Kepadatan-Hirarki

## Deskripsi Proyek (Indonesia Ver.)

Repositori ini merupakan portofolio analisis klastering yang bertujuan untuk mengevaluasi dan membandingkan performa algoritma **HDBSCAN (Hierarchical Density-Based Spatial Clustering of Applications with Noise)** dengan tiga metode klastering hierarki agglomerative, yaitu **Ward linkage**, **Average linkage**, dan **Complete linkage**. Studi ini menggunakan data **Produk Domestik Regional Bruto Atas Dasar Harga Konstan (PDRB ADHK)** Provinsi **Jawa Timur tahun 2023**, yang mencakup **234 observasi** dengan **17 variabel sektoral**.

## Latar Belakang

Data PDRB yang bersifat sektoral dan berskala kabupaten/kota sering kali mengandung pencilan akibat ketimpangan ekonomi antarwilayah. Kondisi ini menantang bagi banyak metode klastering tradisional karena pencilan dapat mengganggu struktur kelompok yang terbentuk. Oleh karena itu, penelitian ini bertujuan untuk mengkaji kekuatan berbagai pendekatan klastering dalam membentuk struktur kelompok yang valid dan berguna, terutama dalam konteks data yang mengandung outlier.

## Metodologi

Metode HDBSCAN dipilih karena kemampuannya dalam membentuk kelompok dengan bentuk tidak reguler serta mendeteksi dan memberi label otomatis pada pencilan. Sebagai pembanding, digunakan tiga metode Hierarchical Agglomerative Clustering (AHC) — Ward, Average, dan Complete linkage — yang merupakan pendekatan klasik dalam pengelompokan berbasis jarak. Evaluasi kualitas hasil klaster dilakukan menggunakan beberapa metrik evaluasi yang komprehensif, yaitu **Silhouette Score**, **Davies-Bouldin Index**, **Calinski-Harabasz Index**, **Dunn Index**, dan **Within-Cluster Sum of Squares (WCSS)**. Metrik-metrik ini dipilih untuk mengukur derajat kompaksi intra-klaster dan separasi antar-klaster, serta mendeteksi pengaruh pencilan terhadap struktur kelompok.

## Hasil dan Temuan

Hasil penelitian menunjukkan bahwa HDBSCAN secara konsisten memberikan performa terbaik dibandingkan ketiga metode agglomerative dalam semua metrik evaluasi yang digunakan. HDBSCAN memperoleh nilai tertinggi pada Silhouette Score sebesar 0.624, Davies-Bouldin Index sebesar 0.492, Calinski-Harabasz Index sebesar 61.465, Dunn Index sebesar 0.696, serta WCSS sebesar 0.789. Nilai-nilai ini mencerminkan bahwa klaster yang dihasilkan oleh HDBSCAN memiliki pemisahan yang jelas antar kelompok, kompak secara internal, dan menunjukkan struktur pengelompokan yang kuat meskipun terdapat pencilan.

Sebaliknya, metode agglomerative seperti Ward, Average, dan Complete linkage belum menunjukkan kinerja optimal dalam menangani pencilan. Ketiga metode tersebut hanya mampu mengelompokkan seluruh data tanpa dapat mengidentifikasi atau menangani pencilan secara eksplisit, sehingga pencilan hanya dimasukkan ke dalam klaster yang ada dan dapat mengganggu validitas struktur kelompok. Meskipun ketiga metode tersebut mampu membentuk kelompok, hasil evaluasi menunjukkan bahwa nilai metriknya tidak setara dengan yang dicapai oleh HDBSCAN pada sebagian besar aspek.

## Kesimpulan

Berdasarkan hasil evaluasi menyeluruh, HDBSCAN terbukti sebagai metode klastering yang paling efektif dalam menghadapi data dengan pencilan, seperti yang terdapat dalam PDRB ADHK Jawa Timur 2023. Keunggulan utama HDBSCAN terletak pada kemampuannya untuk mengelompokkan data dengan fleksibel, menangani bentuk klaster yang tidak beraturan, serta mendeteksi dan memberi label otomatis terhadap outlier. Sementara itu, pendekatan hierarki agglomerative cenderung kurang tangguh dalam konteks data berpencilan. Oleh karena itu, HDBSCAN direkomendasikan sebagai pendekatan utama dalam pengelompokan data ekonomi regional atau data lain yang memiliki sebaran ekstrem dan heterogen.

## Struktur Repositori

- `notebooks/`: notebook eksplorasi dan pemodelan
- `results/`: visualisasi klaster dan evaluasi metrik
- `src/`: skrip utama untuk klastering dan evaluasi

## Project Description (English Ver.)

This repository presents a clustering analysis portfolio aimed at evaluating and comparing the performance of the **HDBSCAN (Hierarchical Density-Based Spatial Clustering of Applications with Noise)** algorithm with three hierarchical agglomerative clustering methods: **Ward linkage**, **Average linkage**, and **Complete linkage**. The study utilizes data from the **Gross Regional Domestic Product at Constant Prices (GRDP ADHK)** of **East Java Province in 2023**, which consists of **234 observations** across **17 sectoral variables**.

## Background

GRDP data, which is sectoral in nature and scaled at the district/city level, often contains outliers due to economic disparities between regions. This poses a challenge for many traditional clustering methods, as outliers can distort the resulting cluster structure. Therefore, this study aims to assess the robustness of various clustering approaches in forming valid and meaningful groupings, particularly in the presence of outliers.

## Methodology

The HDBSCAN method was chosen for its ability to form clusters of arbitrary shapes and to automatically detect and label outliers. As benchmarks, three classical Hierarchical Agglomerative Clustering (HAC) methods — Ward, Average, and Complete linkage — were employed, all of which are based on distance metrics. The clustering results were evaluated using a set of comprehensive metrics: **Silhouette Score**, **Davies-Bouldin Index**, **Calinski-Harabasz Index**, **Dunn Index**, and **Within-Cluster Sum of Squares (WCSS)**. These metrics were selected to assess intra-cluster compactness, inter-cluster separation, and the sensitivity of each method to the presence of outliers.

## Results and Findings

The results demonstrate that HDBSCAN consistently outperformed the three agglomerative methods across all evaluation metrics. HDBSCAN achieved the highest scores with a Silhouette Score of 0.624, a Davies-Bouldin Index of 0.492, a Calinski-Harabasz Index of 61.465, a Dunn Index of 0.696, and a WCSS value of 0.789. These results indicate that the clusters formed by HDBSCAN are well-separated, internally compact, and structurally sound, even in the presence of outliers.

In contrast, the agglomerative methods (Ward, Average, and Complete linkage) did not demonstrate optimal performance in handling outliers. These methods grouped all data points without any mechanism to explicitly detect or manage outliers, resulting in reduced cluster validity. Although these methods succeeded in forming clusters, their performance metrics were generally inferior to those of HDBSCAN in most aspects.

## Conclusion

Based on a comprehensive evaluation, HDBSCAN proved to be the most effective clustering method for handling data with outliers, as seen in the 2023 GRDP ADHK data from East Java. Its main advantages lie in its flexibility to form non-linear cluster shapes, robustness to noise, and automatic outlier labeling. On the other hand, hierarchical agglomerative approaches were less robust in scenarios involving outliers. Therefore, HDBSCAN is recommended as the primary clustering technique for regional economic data or other datasets with extreme or heterogeneous distributions.

## Repository Structure

- `notebooks/`: exploration and modeling notebooks  
- `results/`: clustering visualizations and evaluation metrics  
- `src/`: main scripts for clustering and evaluation
