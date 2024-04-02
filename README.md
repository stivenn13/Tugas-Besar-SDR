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
- Berdasarkan eksplorasi dataset, fitur apa saja yang mempengaruhi kemungkinan serangan jantung?
- Bagaimana mengolah dataset agar dapat dibuat model prediksi kemungkinan serangan jantung?
- Bagaimana cara meningkatkan nilai performa model prediksi kemungkinan serangan jantung?

### Goals
- Mengeksplorasi semua fitur yang tersedia pada dataset kemudian melihat korelasi kemungkinan serangan jantung dari semua fitur yang sedia untuk melihat faktor apa saja yang paling berpengaruh sampai paling kurang berpengaruh terhadap kemungkinan serangan jantung.
- Melakukan proses data wragling dan data preparation terhadap dataset agar dapat dibuat model prediksi kemungkinan serangan jantung.
- Melakukan beberapa variasi model untuk mendapatkan model yang paling baik dari beberapa model yang telah dibuat untuk prediksi kemungkinan serangan jantung.

### Solution Statements
- Untuk eksplorasi fitur dilakukan Analisis Univariat dan Analisis Multivariat. Analisis Univariat dilakukan untuk mengeksploasi data numerik dan data kategorik. Analisis Multivariat dilakukan untuk melihat hubungan antar fitur. Teknik yang digunakan adalah menggunakan catplot, pairplot, dan heatmap untuk melihat Correlation Matrix dari fitur-fitur yang dimiliki.
- Agar didapatkan model prediksi yang baik maka dilakukan proses Data Wragling yang meliputi Data Gathering, Data Assessing, dan Data Cleaning.
- Untuk mengetahui perfoma model dilakukan pengecekan perfoma dengan metrik evaluasi.
