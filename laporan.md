# 🚀 Analisis Sentimen & Topic Modeling E-Commerce
[![Made with SentenceTransformers](https://img.shields.io/badge/Made%20with-SentenceTransformers-blue?style=flat-square)](https://www.sbert.net/)
[![Topic Modeling](https://img.shields.io/badge/Powered%20by-BERTopic-orange?style=flat-square)](https://maartengr.github.io/BERTopic/)
[![Python](https://img.shields.io/badge/Python-3.10%2B-yellow?style=flat-square&logo=python)](https://www.python.org/)

---

## 🎯 **Tujuan**
Proyek ini mengimplementasikan **analisis sentimen otomatis** dan **topic modeling** untuk data ulasan e-commerce.  
Pendekatan ini digunakan untuk memahami opini pelanggan dan mengidentifikasi aspek layanan yang paling sering dipuji atau dikritik.

---

## 🧩 **Dataset**
| Jenis | Jumlah | Deskripsi |
|-------|---------|-----------|
| Berlabel | 49 ulasan (25 positif, 24 negatif) | Untuk melatih model sentimen |
| Non-label | 60 ulasan | Untuk pemodelan topik menggunakan BERTopic |

---

## ⚙️ **Metodologi**
1. Preprocessing teks dasar  
2. Embedding kalimat → `all-MiniLM-L6-v2`  
3. Klasifikasi sentimen → *Logistic Regression*  
4. Topic modeling → *BERTopic (UMAP + HDBSCAN)*  
5. Analisis gabungan → Sentimen per topik  

---

## 📊 **Hasil Utama**

### 🔹 Sentiment Classification
| Metric | Value |
|--------|--------|
| Accuracy | **0.70** |
| F1-macro | 0.70 |
| Precision (neg/pos) | 0.75 / 0.67 |
| Recall (neg/pos) | 0.60 / 0.80 |

📈 *Model baseline cukup stabil untuk dataset kecil. Kesalahan umumnya pada ulasan negatif yang ambigu.*

---

### 🔹 Topic Modeling
Topik utama hasil BERTopic:
1. **Pelayanan & Customer Service** → “ramah”, “membantu”, “cuek”  
2. **Kualitas Produk & Rasa** → “enak”, “puas”, “sesuai”  
3. **Pengiriman & Pembayaran** → “error”, “lambat” *(proporsi negatif tertinggi)*  
4. **Harga & Promo** → variasi opini  

📊 Topik *Pengiriman dan Pembayaran* memiliki sentimen negatif tertinggi (~38–40%).

---

## 💡 **Insight**
- Pelanggan puas dengan **kualitas produk & pelayanan**  
- Keluhan terbanyak pada **sistem pembayaran dan pengiriman**  
- Model mampu menangkap konteks positif/negatif dengan baik meski data terbatas  

---

## 🧭 **Rekomendasi**
1. Tingkatkan sistem pengiriman & transaksi digital  
2. Tambah data berlabel untuk pelatihan ulang model  
3. Fine-tune transformer agar lebih sensitif terhadap bahasa Indonesia informal  
4. Integrasikan hasil analisis ke dashboard monitoring sentimen

---

## 🧠 **Stack Teknologi**
- Python 3.10+  
- pandas, scikit-learn  
- SentenceTransformers  
- BERTopic, HDBSCAN, UMAP  
- matplotlib, joblib  

---

## 📁 **Preview Hasil**
```bash
📊 Accuracy: 0.70
📘 Top 3 Topics: Pelayanan, Pengiriman, Kualitas Produk
😠 Most Negative: Pengiriman & Pembayaran
😃 Most Positive: Kualitas & Pelayanan
```

---

## 🏁 **Kesimpulan**
Proyek ini menunjukkan bahwa kombinasi SentenceTransformer + Logistic Regression + BERTopic efektif untuk memahami opini pelanggan e-commerce.
Dengan peningkatan jumlah data dan fine-tuning model, sistem ini dapat dikembangkan menjadi modul analitik opini pelanggan berbasis AI secara real-time.
