🎓 Insight Learning

Machine Learning Model for Student Learning Pattern Classification

📘 Deskripsi Proyek

Insight Learning merupakan proyek Machine Learning yang bertujuan untuk menganalisis data siswa dan mengelompokkan mereka ke dalam tiga kategori perilaku belajar, yaitu:

🧠 Consistent Learner – siswa dengan pola belajar stabil dan rutin.

⚡ Fast Learner – siswa yang cepat memahami materi namun cenderung cepat kehilangan fokus.

💭 Reflective Learner – siswa yang lebih lambat memproses informasi namun memahami lebih dalam.

Proyek ini bertujuan untuk memberikan insight bagi guru, lembaga pendidikan, dan platform pembelajaran dalam merancang strategi pembelajaran yang lebih adaptif dan personal.

🧩 Tujuan Proyek

Mengembangkan model Machine Learning untuk mengklasifikasikan pola belajar siswa.

Menggunakan data historis siswa (aktivitas, nilai, kehadiran, dll.) untuk menemukan pola tersembunyi.

Menghasilkan rekomendasi berbasis data yang dapat mendukung proses pembelajaran individual.

📂 Struktur Proyek
Insight-Learning/
├── data/
│   ├── processed/
│   │   └── data_cleaned.csv        # hasil preprocessing
│   └── external/                   # file tambahan kecil (opsional)
│
├── notebooks/
│   ├── 01_EDA.ipynb                # eksplorasi data
│   ├── 02_Preprocessing.ipynb      # pembersihan dan transformasi data
│   ├── 03_Model_KNN.ipynb          # model K-Nearest Neighbors
│   ├── 04_Model_NB.ipynb           # model Naive Bayes
│   ├── 05_Evaluation.ipynb         # evaluasi performa model
│   └── utils.ipynb                 # fungsi bantu (opsional)
│
├── src/
│   ├── data_loader.py              # fungsi ambil data dari Google Drive
│   ├── preprocessing.py            # pipeline preprocessing
│   ├── model_knn.py                # definisi dan training model KNN
│   ├── model_nb.py                 # definisi dan training model Naive Bayes
│   └── evaluation.py               # metrik dan visualisasi hasil
│
├── requirements.txt                # daftar library
├── README.md                       # dokumentasi proyek
└── .gitignore                      # file yang diabaikan Git

🚀 Alur Proyek (Revisi)

Data Collection (Pengambilan Data Mentah)
Dataset mentah diambil dari Google Drive dalam bentuk 7 file CSV berikut:

Nama File	Deskripsi Singkat
users.csv	Data seluruh pengguna (pelajar) yang terdaftar di platform.
developer_journeys.csv	Daftar kelas atau kursus yang aktif di platform.
developer_journey_tutorials.csv	Data setiap materi (tutorial) yang termasuk dalam kelas tertentu.
developer_journey_trackings.csv	Aktivitas pelajar saat mengakses materi tutorial.
developer_journey_submissions.csv	Data setiap submission (tugas) yang dikirim oleh pelajar.
developer_journey_completions.csv	Data pelajar yang telah menyelesaikan atau lulus suatu kelas.
exam_results.csv	Nilai akhir atau hasil kuis dari setiap pelajar.

➤ Semua data ini akan digabungkan dan dibersihkan untuk membentuk dataset terpadu sebelum analisis dilakukan.

Data Preprocessing (Prapemrosesan Data)

Menggabungkan tabel berdasarkan user_id dan journey_id untuk membentuk data relasional tunggal.

Menghapus duplikasi dan menangani nilai kosong.

Melakukan transformasi seperti encoding data kategorikal, konversi timestamp ke waktu belajar aktif, serta pembuatan variabel baru (misal: total waktu belajar, jumlah submission, dan hasil kuis rata-rata).

Dataset akhir disimpan sebagai:

data/processed/data_cleaned.csv


Exploratory Data Analysis (EDA)

Analisis deskriptif terkait perilaku belajar siswa.

Visualisasi distribusi skor, aktivitas materi, serta hubungan antara waktu belajar dan hasil evaluasi.

Identifikasi pola yang membedakan consistent, fast, dan reflective learners.

Modeling
Menggunakan dua model utama untuk membedakan kategori siswa:

K-Nearest Neighbors (KNN) — berbasis kedekatan antar siswa.

Naive Bayes (NB) — berbasis probabilitas perilaku belajar.

Model dilatih menggunakan fitur hasil preprocessing seperti:

Frekuensi akses tutorial

Jumlah submission

Total waktu belajar

Rata-rata hasil kuis

Evaluation (Evaluasi Model)
Menggunakan metrik:

Accuracy

F1-score

ROC-AUC

Serta membandingkan performa model KNN dan NB untuk menentukan pendekatan terbaik.

Insight Generation (Penyusunan Insight)

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

Model yang mampu mengklasifikasikan siswa ke dalam tiga tipe learner dengan akurasi optimal.

Visualisasi pola belajar dan hubungan antar fitur.

Insight praktis bagi pendidik untuk meningkatkan efektivitas pembelajaran.

👩‍💻 Pengembang

Nurus Safa’ah
📍 Universitas Negeri Surabaya
📧 [safaahnrs0@gmail.com]

Fadillah Akbar
📍 Universitas Bina Sarana Informatika
📧 [faoedill@gmail.com]
