# 🎓 Insight Learning  
**Machine Learning Model for Student Learning Pattern Classification**

---

## 📘 Deskripsi Proyek
**Insight Learning** adalah proyek Machine Learning yang bertujuan untuk menganalisis data siswa dari sistem pembelajaran digital dan mengelompokkan mereka ke dalam tiga kategori pola belajar utama, yaitu:  
- 🧠 **Consistent Learner** – siswa dengan pola belajar stabil dan rutin.  
- ⚡ **Fast Learner** – siswa yang cepat memahami materi namun cenderung cepat kehilangan fokus.  
- 💭 **Reflective Learner** – siswa yang lebih lambat dalam memahami, tetapi memiliki pemahaman yang lebih mendalam.

Proyek ini menggunakan data interaksi siswa dari berbagai aktivitas pembelajaran (akses materi, submission, kuis, dan hasil evaluasi) untuk menemukan pola belajar yang bermakna dan membantu pendidik dalam membuat strategi pembelajaran yang lebih adaptif.

---

## 🧩 Tujuan Proyek
1. Mengembangkan model Machine Learning untuk mengklasifikasikan pola belajar siswa berdasarkan data aktivitas mereka.  
2. Mengintegrasikan berbagai sumber data siswa menjadi satu dataset analisis.  
3. Memberikan insight berbasis data bagi pendidik untuk mendukung pembelajaran yang lebih personal.  

---

## 📂 Struktur Proyek
```bash
Insight-Learning/
├── data/
│   ├── raw/                               # data mentah dari Google Drive
│   │   ├── users.csv
│   │   ├── developer_journeys.csv
│   │   ├── developer_journey_tutorials.csv
│   │   ├── developer_journey_trackings.csv
│   │   ├── developer_journey_submissions.csv
│   │   ├── developer_journey_completions.csv
│   │   └── exam_results.csv
│   ├── processed/
│   │   └── data_cleaned.csv               # hasil preprocessing
│   └── external/                          # file tambahan (opsional)
│
├── notebooks/
│   ├── 01_EDA.ipynb                       # eksplorasi data
│   ├── 02_Preprocessing.ipynb             # cleaning & transformasi data
│   ├── 03_Model_KNN.ipynb                 # model K-Nearest Neighbors
│   ├── 04_Model_NB.ipynb                  # model Naive Bayes
│   ├── 05_Evaluation.ipynb                # evaluasi & visualisasi
│   └── utils.ipynb                        # fungsi bantu (opsional)
│
├── src/
│   ├── data_loader.py                     # fungsi untuk load data dari Google Drive
│   ├── preprocessing.py                   # pipeline preprocessing
│   ├── model_knn.py                       # definisi model KNN
│   ├── model_nb.py                        # definisi model Naive Bayes
│   └── evaluation.py                      # metrik & hasil evaluasi
│
├── requirements.txt                       # daftar library
├── README.md                              # dokumentasi proyek
└── .gitignore


🚀 Alur Proyek (Revisi)

1. Data Collection (Pengambilan Data Mentah)
Dataset mentah diambil dari Google Drive dalam bentuk 7 file CSV berikut:

Nama File	Deskripsi Singkat
- users.csv	Data seluruh pengguna (pelajar) yang terdaftar di platform.
- developer_journeys.csv	Daftar kelas atau kursus yang aktif di platform.
- developer_journey_tutorials.csv	Data setiap materi (tutorial) yang termasuk dalam kelas tertentu.
- developer_journey_trackings.csv	Aktivitas pelajar saat mengakses materi tutorial.
- developer_journey_submissions.csv	Data setiap submission (tugas) yang dikirim oleh pelajar.
- developer_journey_completions.csv	Data pelajar yang telah menyelesaikan atau lulus suatu kelas.
- exam_results.csv	Nilai akhir atau hasil kuis dari setiap pelajar.

➤ Semua data ini akan digabungkan dan dibersihkan untuk membentuk dataset terpadu sebelum analisis dilakukan.

2. Data Preprocessing (Prapemrosesan Data)

- Menggabungkan tabel berdasarkan user_id dan journey_id untuk membentuk data relasional tunggal.
- Menghapus duplikasi dan menangani nilai kosong.
- Melakukan transformasi seperti encoding data kategorikal, konversi timestamp ke waktu belajar aktif, serta pembuatan variabel baru (misal: total waktu belajar, jumlah submission, dan hasil kuis rata-rata).

Dataset akhir disimpan sebagai:
data/processed/data_cleaned.csv

3. Exploratory Data Analysis (EDA)

- Analisis deskriptif terkait perilaku belajar siswa.
- Visualisasi distribusi skor, aktivitas materi, serta hubungan antara waktu belajar dan hasil evaluasi.
- Identifikasi pola yang membedakan consistent, fast, dan reflective learners.

4. Modeling
  Menggunakan dua model utama untuk membedakan kategori siswa:
    a. K-Nearest Neighbors (KNN) — berbasis kedekatan antar siswa.
    b. Naive Bayes (NB) — berbasis probabilitas perilaku belajar.

  Model dilatih menggunakan fitur hasil preprocessing seperti:
    a. Frekuensi akses tutorial
    b. Jumlah submission
    c. Total waktu belajar
    d. Rata-rata hasil kuis

5. Evaluation (Evaluasi Model)
  Menggunakan metrik:
    a. Accuracy
    b. F1-score
    c. ROC-AUC
  Serta membandingkan performa model KNN dan NB untuk menentukan pendekatan terbaik.

6. Insight Generation (Penyusunan Insight)
  Mengklasifikasikan siswa ke dalam tiga tipe learner:
  🧠 Consistent Learner
  ⚡ Fast Learner
  💭 Reflective Learner
  Menghasilkan insight visual untuk membantu pengambil keputusan (misalnya guru atau platform edukasi) menyesuaikan gaya belajar dan intervensi yang sesuai.

⚙️ Library yang Digunakan
pandas
numpy
matplotlib
seaborn
scikit-learn
google-colab

🧠 Hasil yang Diharapkan

- Model yang mampu mengklasifikasikan siswa ke dalam tiga tipe learner dengan akurasi optimal.
- Visualisasi pola belajar dan hubungan antar fitur.
- Insight praktis bagi pendidik untuk meningkatkan efektivitas pembelajaran.

👩‍💻 Pengembang
Nurus Safa’ah
📍 Universitas Negeri Surabaya
📧 [safaahnrs0@gmail.com]

Fadillah Akbar
📍 Universitas Bina Sarana Informatika
📧 [faoedill@gmail.com]
