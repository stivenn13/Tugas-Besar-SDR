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
- Untuk eksplorasi fitur dilakukan Analisis Univariat dan Analisis Multivariat. Analisis Univariat dilakukan untuk mengeksploasi data numerik dan data kategorik. Analisis Multivariat dilakukan untuk melihat hubungan antar fitur. Teknik yang digunakan adalah menggunakan catplot, pairplot, dan heatmap untuk melihat Correlation Matrix dari fitur-fitur yang dimiliki.
- Agar didapatkan model prediksi yang baik maka dilakukan proses Data Wragling yang meliputi Data Gathering, Data Assessing, dan Data Cleaning.
- Untuk mengetahui perfoma model dilakukan pengecekan perfoma dengan metrik evaluasi.

## Data Understanding
Data diambil dari Kaggle dengan nama *dataset* yaitu *Health care: Heart attack possibility*. URL: https://www.kaggle.com/datasets/nareshbhat/health-care-data-set-on-heart-attack-possibility/data
Kemudian beberapa variabel pada data dimodifikasi membentuk data kategorikal sesuai dengan sumber *dataset* yaitu URL: https://archive.ics.uci.edu/ml/datasets/Heart+Disease

Berikut merupakan detail dari *dataset* yang digunakan untuk pembuatan model:
- Dataset berupa CSV
- Dataset terdiri dari 303 *records* dengan 14 buah variabel yang diukur.
- Dataset terdiri dari 4 data kategori dan 10 data numerik.
- Dataset memiliki *duplicated data* sejumlah 1 records
- Dataset memiliki *missing value* sejumlah 2 records

### Variabel-variabel pada *dataset* adalah sebagai berikut:
- age: umur pasien (dalam tahun)
- sex: jenis kelamin pasien
- cp: tipe chest pain 
- trestbps: tekanan darah ketika istirahat (dalam mm Hg saat masuk rumah sakit)
- chol: kolesterol serum dalam mg/dl
- fbs: gula darah saat puasa > 120 mg/dl (1 = benar; 0 = salah)
- restecg: hasil elektrokardiografi saat istirahat (0 = normal; 1 = mengalami ST-T wave abnormality; 2 = menunjukkan kemungkinan atau pasti hipertrofi ventrikel kiri berdasarkan kriteria Estes)
- thalach: detak jantung maksimum yang tercapai
- exang: angina diinduksi oleh olahraga (1 = benar; 0 = salah)
- oldpeak: ST depression yang disebabkan oleh olahraga dibandingkan istirahat
- slope: kemiringan puncak exercise ST segment
- ca: jumlah pembuluh besar (0-3) yang diwarnai dengan flourosopy
- thal: hasil thallium stress test
- target: 0 = lebih kecil kemungkinan terkena serangan jantung; 1 = lebih besar kemungkinan terkena serangan jantung

Untuk memahami data lebih lanjut, dilakukan Analisis Univariat dan Analisis Multivariat, serta Visualisasi Data

Analisis Univariat merupakan bentuk analisis data yang hanya merepresentasikan informasi yang terdapat pada satu variabel.  Jenis visualisasi ini umumnya digunakan untuk memberikan gambaran terkait distribusi sebuah variabel dalam suatu *dataset*. Sedangkan, Analisis Multivariat tmerupakan jenis analisis data yang terdapat dalam lebih dari dua variabel. Jenis visualisasi ini digunakan untuk merepresentasikan hubungan dan pola yang terdapat dalam multidimensional data. 

Selain melalui analisis, dilakukan juga Visualisasi Data. Memvisualisasikan data memberikan wawasan mendalam tentang perilaku berbagai fitur-fitur yang tersedia dalam *dataset*. 
Teknik visualisasi yang digunakan pada pembuatan model proyek ini adalah dengan menggunakan catplot yang digunakan untuk memplot distribusi data pada data kategori, pairplot yang digunakan untuk melakukan hubungan antar fitur dalam *dataset*, dan heatmap yang menampilkan korelasi antar fitur yang ada dalam *dataset* dalam bentuk matriks.

Berikut adalah hasil Exploratory Data Analysis (EDA), dimana Gambar 1 merupakan EDA Analisis Univariat dan Gambar 2 merupakan EDA Analisis Multivariat.

![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/b16f93d0-fe3f-4f0b-b264-b1310bb0dce9)
###### (i)
![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/cefbbdf0-9c67-47d4-98f4-87cc27f802a2)
###### (ii)
![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/8fed164f-7221-4d37-b78f-3b0b01cb7414)
###### (iii)
![image](https://github.com/stivenn13/Tugas-Besar-SDR/assets/88883271/81233423-5366-4af0-ab36-03b39ec89b2c)![Uploading image.png…]()
###### (iv)
#### Gambar 1.a Analisis Univariat Variabel Categorical Features (i). Variabel 'sex', (ii) Variabel 'cp', (iii) Variabel 'slope', (iv) Variabel 'thal'






