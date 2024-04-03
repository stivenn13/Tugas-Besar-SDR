# Laporan Proyek Machine Learning - Prediksi Posibilitas Serangan Jantung
            
## Business Understanding
Pengembangan model prediksi kemungkinan serangan jantung memiliki potensi dampak atau manfaat untuk membantu individu dan profesional medis dalam mengidentifikasi risiko serangan jantung. Contoh potensi manfaat dari hasil prediksi kemungkinan serangan jantung yang akurat:

Bagi individu:
- Meningkatkan kesadaran diri tentang risiko serangan jantung.
- Mendorong individu untuk mengambil langkah-langkah preventif untuk mengurangi risiko.
- Membantu individu untuk membuat keputusan yang lebih tepat tentang gaya hidup dan perawatan kesehatan.

Bagi profesional medis:
- Meningkatkan kemampuan untuk mengidentifikasi pasien berisiko tinggi.
- Membantu dalam stratifikasi risiko dan skrining.
- Memandu pengambilan keputusan tentang intervensi dan pengobatan.

### Problem Statements
- Berdasarkan eksplorasi *dataset*, fitur apa saja yang mempengaruhi kemungkinan serangan jantung?
- Bagaimana mengolah *dataset* agar dapat dibuat model prediksi kemungkinan serangan jantung?
- Bagaimana cara mengevaluasi nilai performa model prediksi kemungkinan serangan jantung?

### Goals
- Mengeksplorasi semua fitur yang tersedia pada dataset kemudian melihat korelasi kemungkinan serangan jantung dari semua fitur yang sedia untuk melihat faktor apa saja yang paling berpengaruh sampai paling kurang berpengaruh terhadap kemungkinan serangan jantung.
- Melakukan proses data wragling dan data preparation terhadap dataset agar dapat dibuat model prediksi kemungkinan serangan jantung.
- Melakukan beberapa variasi model untuk mendapatkan model yang paling baik dari beberapa model yang telah dibuat untuk prediksi kemungkinan serangan jantung.

### Solution Statements
- Untuk eksplorasi fitur dilakukan Analisis Univariat dan Analisis Multivariat. Analisis Univariat dilakukan untuk mengeksplorasi data numerik dan data kategorik. Analisis Multivariat dilakukan untuk melihat hubungan variabel kategorik dengan variabel 'target'. Teknik yang digunakan adalah menggunakan catplot dan pairplot. Juga Analisis Multivariat dilakukan untuk melihat hubungan dari setiap variabel numerik menggunakan teknik heatmap untuk melihat Correlation Matrix dari fitur-fitur yang dimiliki.
- Agar didapatkan model prediksi yang baik maka dilakukan proses Data Wragling yang meliputi Data Gathering, Data Assessing, dan Data Cleaning.
- Untuk mengetahui perfoma model dilakukan pengecekan perfoma dengan mengetahui tingkat akurasi dan melalui metrik evaluasi.

## Data Understanding
Data diambil dari Kaggle dengan nama *dataset* yaitu *Health care: Heart attack possibility*. 
URL: https://www.kaggle.com/datasets/nareshbhat/health-care-data-set-on-heart-attack-possibility/data

Kemudian beberapa variabel pada data dimodifikasi membentuk data kategorikal sesuai dengan sumber *dataset* yaitu URL: https://archive.ics.uci.edu/ml/datasets/Heart+Disease

Berikut merupakan detail dari *dataset* yang digunakan untuk pembuatan model:
- Dataset berupa CSV
- Dataset terdiri dari 303 *records* dengan 14 buah variabel yang diukur.
- Dataset terdiri dari 9 data kategorik (5 di antaranya sudah diubah menjadi data numerik) dan 5 data numerik.
- Dataset memiliki *duplicated data* sejumlah 1 records
- Dataset memiliki *missing value* sejumlah 2 records

### Variabel-variabel pada *dataset* adalah sebagai berikut:
- age: umur pasien (dalam tahun)
- sex: jenis kelamin pasien
- cp: tipe chest pain 
- trestbps: tekanan darah ketika istirahat (dalam mm Hg saat masuk rumah sakit)
- chol: kolesterol serum dalam mg/dl
- fbs: gula darah (trigliserida) saat puasa gula > 120 mg/dl (1 = benar; 0 = salah)
- restecg: hasil elektrokardiografi saat istirahat (0 = normal; 1 = mengalami ST-T wave abnormality; 2 = menunjukkan kemungkinan atau pasti hipertrofi ventrikel kiri berdasarkan kriteria Estes)
- thalach: detak jantung maksimum yang tercapai
- exang: angina diinduksi oleh olahraga (1 = benar; 0 = salah)
- oldpeak: ST depression yang disebabkan oleh olahraga dibandingkan istirahat
- slope: kemiringan puncak exercise ST segment
- ca: jumlah pembuluh besar (0-3) yang diwarnai dengan flourosopy
- thal: hasil thallium stress test
- target: 0 = lebih kecil kemungkinan terkena serangan jantung; 1 = lebih besar kemungkinan terkena serangan jantung

Untuk memahami data lebih lanjut, dilakukan Analisis Univariat, Analisis Multivariat, dan Visualisasi Data

Analisis Univariat merupakan bentuk analisis data yang hanya merepresentasikan informasi yang terdapat pada satu variabel.  Jenis visualisasi ini umumnya digunakan untuk memberikan gambaran terkait distribusi sebuah variabel dalam suatu *dataset*. Sedangkan Analisis Multivariat melibatkan lebih dari dua variabel. Jenis visualisasi ini digunakan untuk merepresentasikan hubungan dan pola yang terdapat dalam multidimensional data. 

Selain melalui analisis, dilakukan juga Visualisasi Data. Memvisualisasikan data memberikan wawasan mendalam tentang perilaku berbagai fitur-fitur yang tersedia dalam *dataset*. Teknik visualisasi yang digunakan pada pembuatan model proyek ini adalah dengan menggunakan catplot yang digunakan untuk memplot distribusi data pada data kategori, pairplot yang digunakan untuk melakukan hubungan antar fitur dalam *dataset*, dan heatmap yang menampilkan korelasi antar fitur yang ada dalam *dataset* dalam bentuk matriks.

Berikut adalah hasil Exploratory Data Analysis (EDA), dimana Gambar 1 merupakan EDA Analisis Univariat dan Gambar 2 merupakan EDA Analisis Bivariat.

![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/b16f93d0-fe3f-4f0b-b264-b1310bb0dce9)
###### (i)
![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/cefbbdf0-9c67-47d4-98f4-87cc27f802a2)
###### (ii)
![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/8fed164f-7221-4d37-b78f-3b0b01cb7414)
###### (iii)
![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/81233423-5366-4af0-ab36-03b39ec89b2c)
###### (iv)
#### Gambar 1.a Analisis Univariat Variabel Kategorik (i). Variabel 'sex', (ii) Variabel 'cp', (iii) Variabel 'slope', (iv) Variabel 'thal'

![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/09ec247d-14df-44ef-9470-89e95e8d83b9)
#### Gambar 1.b Analisis Univariat Variabel Numerik

Pada Gambar 1.a, (i) grafik menampilkan batang oranye yang mencapai sedikit di atas angka 100 pada sumbu “count”, menunjukkan ada sedikit lebih dari 100 wanita, (ii) grafik menampilkan distribusi jenis nyeri dada yang menunjukkan bahwa “typical angina” adalah yang paling umum, diikuti oleh “non-anginal pain,” “atypical angina,” dan “asymptomatic.”, (iii) grafik menunjukkan sebagian besar slope memiliki kemiringan menurun dan rata dibanding kemiringan meningkat., (iv) grafik menunjukkan bahwa persentase fixed defect paling tinggi, diikuti dengan reversible defect dan normal. 

Pada Gambar 1.b, Data numerik tidak terdistribusi secara normal. Ada hubungan yang kompleks antara variabel 'target' dan variabel lainnya. Diperlukan analisis lebih lanjut untuk memahami hubungan antara variabel 'target' dan variabel lainnya.

Setelah itu dilakukan juga Analisis Multivariat untuk setiap variabel kategorik terhadap variabel 'target'.

![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/29f8cf5f-8211-4627-baf0-f71c2e456aab)
###### (i)
![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/b27b0b5c-c9ab-401c-8092-3d297a9b366c)
###### (ii)
![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/53d42651-057f-4763-8a65-47ef15887cd5)
###### (iii)
![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/197809af-b686-4e82-baa3-aefc336f3639)
###### (iv)
#### Gambar 2.a Analisis Multivariat Variabel Kategorik terhadap Variabel 'target' (i). Variabel 'sex', (ii) Variabel 'cp', (iii) Variabel 'slope', (iv) Variabel 'thal'

Pada Gambar 2.a (i) dapat dilihat bahwa rata-rata "Target" lebih tinggi pada wanita dibandingkan pria, (ii) dapat dilihat bahwa rata-rata "Target" bervariasi berdasarkan tingkat nyeri dada, dengan kelompok "Typical Angina" memiliki rata-rata tertinggi dan kelompok "Asymptomatic" memiliki rata-rata terendah, (iii) hal ini menunjukkan bahwa variabel 'slope' mungkin memiliki hubungan linear dengan "Target", di mana nilai "Target" yang lebih tinggi dikaitkan dengan kemiringan 'upsloping' dan nilai "Target" yang lebih rendah dikaitkan dengan kemiringan 'downsloping', (iv) hal ini menunjukkan bahwa hasil thallium stress test mungkin memiliki hubungan linear dengan "Target", di mana nilai "Target" yang lebih tinggi dikaitkan dengan reversible defect dan nilai "Target" yang lebih rendah dikaitkan dengan normal.

Setelah itu, dilakukan juga Analisis Multivariat untuk melihat hubungan antara setiap variabel numerik menggunakan plot grafik dan matriks korelasi.

![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/d53ee248-ba80-48d5-962a-f5da0e2ed935)
#### Gambar 2.b Analisis Multivariat Variabel Numerik

![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/52f31a6b-5ed7-4c8f-b1fa-62c1d97e4c54)
#### Gambar 2.c Matriks Korelasi Variabel Numerik

Pada Gambar 2.b  terdapat beberapa hubungan yang terlihat jelas, seperti: korelasi positif antara usia dan tekanan darah (trestbps), korelasi positif antara kolesterol (chol) dan trigliserida (fbs), korelasi positif antara denyut jantung istirahat (restecg) dan denyut jantung maksimal (thalach). Lalu pada Gambar 2.c dapat diamati bahwa variabel dengan korelasi paling kuat untuk korelasi negatif dengan "Target" adalah denyut jantung maksimal (thalach) dan korelasi paling kuat untuk korelasi positif dengan "Target" adalah jumlah major vessels (0-3) colored by flourosopy (ca).

## Data Preparation
Pada proses Data Preparation dilakukan kegiatan seperti Data Gathering, Data Assessing, dan Data Cleaning. Pada proses Data Gathering, data diimpor sedemikian rupa agar bisa dibaca dengan baik menggunakan dataframe Pandas. Untuk proses Data Assessing, berikut adalah beberapa pengecekan yang dilakukan:
- Duplicate data (data yang serupa dengan data lainnya)
- Missing value (data atau informasi yang "hilang" atau tidak tersedia)

Pada proses Data Cleaning, secara garis besar, terdapat tiga metode yang dapat digunakan antara lain seperti berikut:
- Dropping (metode yang dilakukan dengan cara menghapus sejumlah baris data)
- Imputation (metode yang dilakukan dengan cara mengganti nilai yang "hilang" atau tidak tersedia dengan nilai tertentu yang bisa berupa median atau mean dari data)

## Modelling
Dilakukan beberapa jenis Machine Learning Modelling yaitu Logistic Regression, Naive Bayes, Random Forest Classifier, Extreme Gradient Boost, Decision Tree, dan Support Vector Machine. 

### Logistic Regression
Logistic Regression adalah algoritma Supervised Machine Learning yang digunakan untuk tugas klasifikasi biner. LR memprediksi kemungkinan terjadinya suatu peristiwa dengan menganalisis hubungan antara satu atau lebih variabel independen dan variabel dependen biner. Model ini menggunakan fungsi logistik, yang mengubah keluaran menjadi probabilitas antara 0 dan 1, untuk memperkirakan kemungkinan terjadinya peristiwa. Regresi logistik banyak digunakan di berbagai bidang, termasuk kesehatan, pemasaran, keuangan, dan banyak lagi, karena kemudahan implementasi dan interpretasinya[[1](https://journals.lww.com/crst/fulltext/2021/07000/logistic_regression__a_simple_primer.24.aspx)].

### Naive Bayes
Naive Bayes adalah metode klasifikasi yang berakar pada teorema Bayes. Metode ini menggunakan probabilitas dan statistik untuk memprediksi peluang di masa depan berdasarkan pengalaman di masa sebelumnyaIndependensi yang kuat adalah asumsi dasar dalam Naive Bayes, yang berarti kondisi antar atribut saling bebas atau tidak saling berkaitan[[2](https://jurnal.fmipa.unmul.ac.id/index.php/SNMSA/article/download/520/217/)].

### Random forest Classifier
Random Forest adalah metode klasifikasi yang menggunakan kumpulan pohon keputusan (decision trees) untuk memprediksi label kelas pada data yang belum diberi label. Metode ini telah menarik perhatian peneliti karena akurasi tinggi dan keunggulannya dalam meningkatkan kinerja [[3](https://ejurnal.its.ac.id/index.php/sains_seni/article/download/48517/5833)].

### Extreme Gradient Boost
XGBoost, juga disebut sebagai Extreme Gradient Boosting, adalah algoritma pembelajaran ansambel yang menggunakan konsep “peningkatan gradien dengan pohon keputusan”, di mana kepentingan setiap pohon keputusan dihitung dan ditambahkan ke ansambel. XGBoost termasuk dalam kelompok algoritma peningkatan, yang menggabungkan prediksi beberapa Learning yang lemah (biasanya pohon keputusan) untuk menciptakan model prediksi yang kuat [[4](https://journals.nawroz.edu.krd/index.php/ajnu/article/view/1612)].

### Decision Tree
Decision Tree adalah algoritma Supervised Machine Learning yang digunakan untuk tugas klasifikasi dan regresi. Decision Tree memodelkan keputusan berdasarkan kondisi tertentu. Struktur pohon terdiri dari node (mewakili fitur atau atribut), edge (mewakili node penghubung), dan daun (mewakili label kelas atau nilai regresi) [[5](https://link.springer.com/article/10.1007/s10462-011-9272-4)].

### Support Vector Machine
SVM adalah algoritma Supervised Machine Learning yang digunakan untuk tugas klasifikasi dan regresi. Tujuan utamanya adalah menemukan hyperplane optimal dalam ruang berdimensi N yang memisahkan titik data ke dalam kelas berbeda. Hyperplane memaksimalkan margin antara titik terdekat dari kelas yang berbeda. SVM kuat terhadap outlier dan dapat menangani data berdimensi tinggi dan hubungan nonlinier [[6](https://link.springer.com/chapter/10.1007/978-1-4302-5990-9_3)]

## Evaluation
Pada Proyek ini, dilakukan Evaluasi untuk setiap Model ML dengan dua cara yaitu dengan mengetahui tingkat akurasi dari setiap model dan memeriksa metriks juga melakukan prediksi dari model yang sudah di ensemble dan model yang tidak di ensemle. 

![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/25bd165a-8de1-4c24-b75c-fadbe693be13)
###### Gambar 3 Perolehan Tingkat Akurasi dari Setiap ML Model

![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/6c06417f-db33-40a9-9a5b-358e99a493fa)
###### Gambar 4 Barplot Representasi Akurasi dari Setiap ML Model

Berdasarkan perolehan tingkat akurasi dan barplot akurasi untuk setiap model diatas menyatakan bahwa model Logistic Regression, Random Forest, dan Support Vector Machine memiliki tingkat akurasi paling tinggi. Maka itu, dilakukan ensemble terhadap ketiga Model tersebut untuk membentuk model baru yang lebih bagus.

![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/825c6056-6dec-406b-b213-fc8a531aacec)
###### Gambar 5 Perolehan Tingkat Akurasi dari Model yang sudah di-Ensemble

Dapat dilihat bahwa teknik Ensemble ML Model berhasil mendapatkan ML Model baru dengan tingkat akurasi yang lebih tinggi. Setelah itu, akan diperiksa metriks dan melakukan prediksi dari model yang sudah di-Ensemble dan model yang tidak di-Ensemble. 

![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/c4df7077-54cb-4c29-8dee-c05ec0c6e64e)
###### Gambar 6 Performa Model

![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/97d6da97-b372-49ba-b28c-cabd62c39571)
###### Gambar 7 Hasil Prediksi Model

Berdasarkan hasil prediksi diatas, ML Models Decision Tree dan Ensembled Model (SCV) memiliki hasil prediksi yang paling dekat dengan nilai y_true. 

Berdasarkan hasil evaluasi ML Models dengan tingkat akurasi dan melihat hasil prediksi dari setiap ML Models, dapat disimpulkan bahwa prediksi Ensembled Model-lah yang paling cocok untuk digunakan

## Referensi:
[1] Pal, Ankita. Logistic regression: A simple primer. Cancer Research, Statistics, and Treatment 4(3):p 551-554, Jul–Sep 2021. | DOI: 10.4103/crst.crst_164_21 

[2] AZIZAH, Nur; GOEJANTORO, Rito; SIFRIYANI, Sifriyani. METODE NAIVE BAYES DENGAN PENDEKATAN DISTRIBUSI GAUSS UNTUK KLASIFIKASI PEMINATAN PESERTA DIDIK. Prosiding Seminar Nasional Matematika dan Statistika, [S.l.], v. 1, p. 8-14, may 2019. ISSN 2657-232X. Available at: <https://jurnal.fmipa.unmul.ac.id/index.php/SNMSA/article/view/520>. Date accessed: 03 apr. 2024.

[3] L. Ratnawati and D. R. Sulistyaningrum, “Penerapan Random Forest Untuk Mengukur Tingkat Keparahan Penyakit Pada Daun apel,” Jurnal Sains dan Seni ITS, vol. 8, no. 2, Jan. 2020. doi:10.12962/j23373520.v8i2.48517 

[4] Z. Arif Ali, Z. H. Abduljabbar, H. A. Taher, A. Bibo Sallow, and S. M. Almufti, “Exploring the Power of eXtreme Gradient Boosting Algorithm in Machine Learning: a Review”, ACAD J NAWROZ UNIV, vol. 12, no. 2, pp. 320–334, May 2023.

[5] Kotsiantis, S.B. Decision trees: a recent overview. Artif Intell Rev 39, 261–283 (2013). https://doi.org/10.1007/s10462-011-9272-4

[6] Awad, M., Khanna, R. (2015). Support Vector Machines for Classification. In: Efficient Learning Machines. Apress, Berkeley, CA. https://doi.org/10.1007/978-1-4302-5990-9_3
