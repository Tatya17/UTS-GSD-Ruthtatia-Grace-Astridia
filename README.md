# UTS Graf Sains Data (GSD) 2026/2027

Repository ini berisi selengkapnya pengerjaan **Ujian Tengah Semester (UTS) Graf dan Sains Data (GSD)**. Proyek ini mencakup pemrosesan data *e-commerce* (*RetailRocket dataset*), ingesti data ke database graf Neo4j, analisis *Vector Space Modeling* (VSM), hingga pemodelan serta evaluasi sistem rekomendasi berbasis *User-based KNN Collaborative Filtering*.

* **Nama Mahasiswa:** Ruthtatia Grace Astridia
* **NIM:** 24031554072
* **Program Studi:** S1 Sains Data
* **Instansi:** Universitas Negeri Surabaya (UNESA)
* **Mata Kuliah:** Graf dan Sains Data (GSD)

# Keterangan File:

* README.md
  File dokumentasi utama yang menjelaskan gambaran umum proyek, alur pengerjaan, skema database, pemodelan sistem rekomendasi, serta petunjuk penggunaan repository.
* UTS_Ruthtatia Grace.ipynbNotebook Jupyter utama yang berisi seluruh kode program Python, perintah kueri Cypher SQL, output eksekusi, grafik visualisasi NetworkX, serta narasi penjelasan ilmiah dari Soal Nomor 1 hingga Soal Nomor 8 dan bagian Analytics (KNN & Evaluasi Metrik).
* events_filtered.zip
  Berkas terkompresi yang berisi dataset events_filtered.csv hasil penyaringan berdasarkan rentang waktu UNIX timestamp untuk periode Training (P1: 20 Mei 2015 - 20 Juni 2015) dan Testing (P2: 21 Juli 2015 - 31 Agustus 2015).
* requirements.txt
  Berisi daftar pustaka (dependencies/libraries) Python yang dibutuhkan untuk menjalankan eksperimen pada notebook (seperti pandas, numpy, scipy, scikit-learn, neo4j, networkx, matplotlib, dan tqdm).

# Ringkasan Alur Pengerjaan & Metodologi

* Data Preprocessing & Filtering: Pemfilteran dataset mentah RetailRocket menggunakan kurun waktu timestamp milidetik untuk memisahkan subset periode P1 (Training) dan P2 (Testing).
* Neo4j Graph Ingestion: Data diimpor ke database Neo4j (neo4j://127.0.0.1:7687) menjadi Labeled Property Graph dengan simpul :Visitor dan :Item, serta relasi :VIEWED, :ADDED_TO_CART, dan :BOUGHT.
* Subgraph Analysis & VSM: Analisis komposisi simpul/relasi, pemodelan VSM User vs VSM Item, serta visualisasi Bipartite Graph menggunakan NetworkX.
* Similarity Calculation & Projection: Kalkulasi Cosine Similarity berbasis Sparse Matrix (csr_matrix) dan penyuntingan relasi :SIMILAR_TO beserta properti score ke Neo4j.
* Recommendation & Evaluation: Pemodelan User-based KNN Collaborative Filtering (k=5) pada pengguna acak (Visitor 1203832) dan evaluasi metrik Hit@5 & NDCG@5.
