# Analisis Sentimen dan Topic Modeling - Project Challenge PRIMA PTKI
**Author:** Heriswaya  
**Program:** Bootcamp AI PRIMA PTKI (Sesi 8)  
**Tanggal:** November 2025  

---

## 🎯 Tujuan Proyek
Proyek ini bertujuan membangun sistem **analisis sentimen otomatis** dan **topic modeling** pada data ulasan e-commerce.  
Pendekatan ini membantu memahami aspek yang paling sering dipuji atau dikeluhkan pelanggan berdasarkan teks ulasan.

---

## 🧩 Dataset
| Jenis Data | Jumlah | Deskripsi |
|-------------|---------|-----------|
| Labeled | 49 ulasan (25 positif, 24 negatif) | Digunakan untuk melatih model klasifikasi sentimen |
| Non-labeled | 60 ulasan | Digunakan untuk analisis topik menggunakan BERTopic |

---

## ⚙️ Metodologi
1. **Preprocessing:** pembersihan teks sederhana (lowercase, hapus karakter non-alfabet).  
2. **Embedding:** menggunakan model `SentenceTransformer (all-MiniLM-L6-v2)` untuk representasi teks.  
3. **Klasifikasi Sentimen:** model Logistic Regression dilatih pada data berlabel.  
4. **Topic Modeling:** menggunakan `BERTopic` dengan UMAP + HDBSCAN pada data non-label.  
5. **Analisis Gabungan:** prediksi sentimen diterapkan pada hasil topik untuk melihat proporsi sentimen per topik.

---

## 📊 Hasil Utama

### 🔹 Klasifikasi Sentimen
| Metric | Value |
|--------|--------|
| Accuracy | **0.70** |
| F1-score (macro) | 0.70 |
| Precision (neg/pos) | 0.75 / 0.67 |
| Recall (neg/pos) | 0.60 / 0.80 |

Confusion Matrix:
[[3 2]
[1 4]]

Interpretasi singkat:  
Model berhasil memisahkan kelas positif dan negatif dengan akurasi 70%.  
Kesalahan masih terjadi pada teks negatif yang ambigu atau terlalu singkat.  
Untuk dataset kecil, model baseline ini sudah menunjukkan performa yang cukup stabil.

---

### 🔹 Topic Modeling (BERTopic)
Beberapa topik dominan yang ditemukan:
1. **Pelayanan & Customer Service** — sering disebut dalam konteks “ramah”, “membantu”, dan “cuek”.  
2. **Kualitas Produk & Rasa** — banyak ulasan positif dengan kata “enak”, “puas”, “sesuai”.  
3. **Pengiriman & Pembayaran** — topik dengan proporsi negatif tertinggi (“error”, “lambat”).  
4. **Harga & Promo** — opini bervariasi, sebagian menilai murah, sebagian tidak sesuai ekspektasi.

---

## 💡 Interpretasi
- Topik dengan proporsi negatif tertinggi adalah **Pengiriman** dan **Sistem Pembayaran**.  
- Pelanggan cenderung puas terhadap kualitas produk dan pelayanan, namun masih banyak keluhan soal kecepatan pengiriman dan error transaksi.  
- Model sudah mampu menangkap pola sentimen dengan baik, meskipun ukuran dataset masih terbatas.

---

## 🔁 Rekomendasi
1. **Perbaiki sistem pembayaran dan pengiriman**, karena paling sering dikritik.  
2. **Tambah data ulasan berlabel** untuk meningkatkan akurasi model.  
3. **Lakukan fine-tuning** pada transformer agar lebih peka terhadap konteks Bahasa Indonesia.  
4. Gunakan hasil ini sebagai dasar untuk **dashboard pemantauan sentimen pelanggan**.

---

## 📂 Struktur Repository
AI-PRIMA-PTKI-ProjectChallenge-Heriswaya/
│
├── Heriswaya_ProjectChallengeAssigment_Sesi8.ipynb # Notebook utama
├── laporan.md # Laporan lengkap proyek
├── labeled_clean.csv # Dataset labeled setelah pembersihan
├── nonlabel_topic_sentiment.csv # Hasil prediksi sentimen + topik
├── sentiment_clf_lr.joblib # Model klasifikasi Logistic Regression
├── bertopic_model/ # Model topic modeling tersimpan
└── README.md # Dokumentasi ini

---

## 🧠 Tools & Library
- Python 3.10+  
- pandas, scikit-learn, sentence-transformers  
- bertopic, hdbscan, umap-learn, nltk  
- matplotlib, joblib  

---

## ✉️ Submission
**Email submit:** digital_bootcamp@ecc.co.id  
**Subject:** `[Heriswaya] - Tugas Proyek 2 – PRIMA PTKI`  
**Deadline:** 14 November 2025, 23:59 WIB

---

## 🏁 Kesimpulan
Model Logistic Regression dengan embedding `all-MiniLM-L6-v2` berhasil mengklasifikasikan sentimen ulasan e-commerce dengan akurasi **70%**.  
Analisis topik menunjukkan area utama untuk perbaikan, yaitu **pengiriman dan sistem pembayaran**.  
Proyek ini menjadi langkah awal dalam pengembangan sistem analitik opini pelanggan yang data-driven dan otomatis.
