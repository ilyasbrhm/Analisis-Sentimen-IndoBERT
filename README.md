# 📱 Analisis Sentimen Aplikasi MyTelkomsel dengan IndoBERT

Proyek ini bertujuan untuk menganalisis sentimen pengguna terhadap aplikasi **MyTelkomsel** di Google Play Store menggunakan pendekatan machine learning berbasis **IndoBERT**, model BERT yang dioptimalkan untuk Bahasa Indonesia.

---

## 🧠 Tujuan

- Mengklasifikasikan sentimen pengguna menjadi **positif**, **netral**, atau **negatif**
- Memberikan **insight** terhadap pengembang berdasarkan ulasan pengguna
- Membangun sistem **inference interaktif** berbasis IndoBERT

---

## 📊 Dataset

- Sumber: Google Play Store (Aplikasi MyTelkomsel)
- Jumlah ulasan: 10.000
- Bahasa: Indonesia
- Fitur: `ulasan`, `rating`, `tanggal`
- Format: `.csv` hasil scraping dengan `google-play-scraper`

---

## 📦 Library yang Digunakan

- `google-play-scraper`
- `pandas`, `numpy`, `matplotlib`, `seaborn`
- `wordcloud`
- `scikit-learn`
- `transformers`, `datasets` (HuggingFace)
- `torch` (PyTorch)

---

## 🔁 Alur Metodologi (CRISP-DM)

1. **Business Understanding**  
   Menjawab permasalahan banyaknya ulasan negatif pada aplikasi MyTelkomsel.

2. **Data Understanding**  
   Melakukan scraping dan eksplorasi data: distribusi rating, WordCloud, dsb.

3. **Data Preparation**  
   - Pembersihan teks (`clean_text`)
   - Pelabelan sentimen berdasarkan rating
   - Oversampling untuk mengatasi ketidakseimbangan kelas
   - Encoding label dan tokenisasi

4. **Modeling**  
   - Model: `indobenchmark/indobert-base-p1`
   - Training menggunakan HuggingFace `Trainer`
   - 3 epoch, learning rate `2e-5`, batch size `8`

5. **Evaluation**  
   - Akurasi validasi: **94.08%**
   - F1-score macro average: **91%**
   - Confusion Matrix & Classification Report

---

## 📈 Hasil Evaluasi

| Metric        | Value   |
|---------------|---------|
| Accuracy      | 94.08%  |
| F1-Score      | 91.00%  |
| Epochs        | 3       |
| Model         | IndoBERT|

Contoh output confusion matrix dan inference juga tersedia di notebook.

---

## 🔍 Inference Interaktif

Kamu bisa langsung memasukkan kalimat dan mendapatkan hasil sentimen berikut confidence-nya:

```bash
Masukkan ulasan: Aplikasi ini sangat membantu saya!
→ Sentimen: positif (Confidence: 0.95)
