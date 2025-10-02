# 📡 Proyek Prediksi Customer Churn Perusahaan Telekomunikasi

## 1. Project Introduction
Proyek ini merupakan *Capstone Project* untuk Modul 2 program AI Engineering di Purwadhika Digital Technology School. Tujuannya adalah untuk membangun sebuah model *machine learning* secara *end-to-end* yang mampu memprediksi pelanggan mana yang kemungkinan besar akan berhenti berlangganan (*churn*) dari sebuah perusahaan telekomunikasi fiktif.

Proyek ini mencakup seluruh siklus hidup ilmu data, mulai dari perumusan masalah bisnis, pembersihan dan persiapan data, *feature engineering*, pelatihan dan evaluasi berbagai model, hingga analisis dampak bisnis dari model yang diusulkan.

## 2. Business Problem & Objective
* **Problem**: Di industri telekomunikasi yang sangat kompetitif, kehilangan pelanggan (*customer churn*) adalah masalah serius yang berdampak langsung pada pendapatan. Biaya untuk mengakuisisi pelanggan baru jauh lebih mahal daripada mempertahankan pelanggan yang sudah ada.
* **Objective**: Tujuan utama proyek ini adalah membangun model klasifikasi untuk mengidentifikasi pelanggan yang berisiko tinggi akan *churn*. Dengan identifikasi dini, tim retensi dapat secara proaktif menawarkan insentif yang tepat untuk mempertahankan mereka, sehingga dapat menekan *churn rate* dan meningkatkan profitabilitas perusahaan.

## 3. Metodologi Proyek
Proyek ini dikerjakan melalui beberapa tahapan utama:
1.  **Data Cleaning**: Memastikan data konsisten, bebas dari duplikasi, dan siap untuk dianalisis.
2.  **Exploratory Data Analysis (EDA)**: Melakukan visualisasi untuk memahami hubungan antara berbagai fitur pelanggan dengan status *churn*.
3.  **Feature Engineering**: Mengubah data mentah menjadi fitur yang informatif untuk model, termasuk:
    * **Encoding**: Mengubah fitur kategorikal menjadi numerik (menggunakan *Ordinal* dan *One-Hot Encoding*).
    * **Feature Creation**: Menciptakan fitur-fitur baru yang cerdas seperti `ProfilRisiko`, `EstimatedTotalCharges`, dan `JumlahLayanan` untuk menangkap sinyal prediksi yang lebih kuat.
4.  **Modeling**: Melatih dan membandingkan performa dari 6 model klasifikasi yang berbeda, yaitu: Logistic Regression, Random Forest, XGBoost, Support Vector Machine, K-Nearest Neighbors, dan Naive Bayes.
5.  **Evaluation**: Mengevaluasi model menggunakan berbagai metrik, dengan fokus utama pada **Recall** untuk memaksimalkan deteksi pelanggan yang berisiko *churn*.
6.  **Business Impact Simulation**: Melakukan simulasi sederhana untuk mengestimasi potensi penghematan finansial dari implementasi model.

## 4. Key Results & Findings
* Model terbaik yang terpilih adalah **Naive Bayes**, yang secara signifikan mengungguli model lain dalam metrik bisnis utama. Model ini berhasil mencapai **Recall sebesar 80%** pada data uji, yang berarti mampu mengidentifikasi 8 dari 10 pelanggan yang sebenarnya akan *churn*.
* Fitur yang paling berpengaruh dalam memprediksi *churn* adalah fitur-fitur yang baru diciptakan, terutama yang berkaitan dengan nilai finansial pelanggan seperti `EstimatedTotalCharges` dan `BiayaPerLayanan`.
* Simulasi dampak bisnis menunjukkan bahwa dengan mengimplementasikan model Naive Bayes, perusahaan diestimasikan dapat memperoleh **penghematan bersih sekitar $4,272 per bulan**, setelah memperhitungkan biaya kampanye retensi (dengan asumsi keberhasilan 60% dan biaya penawaran 15%).

## 5. Tech Stack
* **Python 3**
* **Jupyter Notebook**
* **Pandas & NumPy**: Untuk manipulasi dan analisis data.
* **Matplotlib & Seaborn**: Untuk visualisasi data.
* **Scikit-learn**: Untuk *preprocessing*, pemodelan, dan evaluasi.
* **XGBoost**: Untuk pemodelan.

## 6. Struktur File
```
.
├── capstone_2_thariq_ahmad.ipynb   # Notebook utama berisi seluruh analisis
├── final_model.pkl                 # File model Naive Bayes yang sudah disimpan
├── WA_Fn-UseC_-Telco-Customer-Churn.csv # Dataset mentah yang digunakan
└── README.md                       # Anda sedang membaca file ini
```

## 7. Cara Reproduksi Proyek
Untuk menjalankan notebook ini di lingkungan lokal Anda, ikuti langkah-langkah berikut:
1.  **Clone repository ini:**
    ```bash
    git clone [URL_REPOSITORY_ANDA]
    cd [NAMA_FOLDER_REPOSITORY]
    ```
2.  **Buat dan aktifkan virtual environment:**
    ```bash
    python -m venv venv
    # Windows
    .\venv\Scripts\activate
    # macOS/Linux
    source venv/bin/activate
    ```
3.  **Instal dependensi yang diperlukan:**
    Buat file `requirements.txt` dengan konten di bawah ini, lalu jalankan `pip install`.
    ```txt
    pandas
    numpy
    matplotlib
    seaborn
    scikit-learn
    xgboost
    jupyter
    ```
    ```bash
    pip install -r requirements.txt
    ```
4.  **Jalankan Jupyter Notebook:**
    ```bash
    jupyter notebook
    ```
    Buka file `capstone_2_thariq_ahmad.ipynb` dan jalankan sel-selnya secara berurutan. Pastikan file dataset `WA_Fn-UseC_-Telco-Customer-Churn.csv` berada di direktori yang sama.
