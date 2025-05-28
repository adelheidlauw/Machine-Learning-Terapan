# Laporan Proyek Machine Learning - Adelheid Chantal Lauw

## Domain Proyek

Penyakit kardiovascular diseases (*Cardiovascular diseases* (CVDs)) merupakan penyebab kematian nomor satu di dunia. 
Pada tahun 2019, CVDs menyebabkan kira-kira 17.9 juta orang meninggal, di mana ini sekitar 32% dari semua penyebab kematian. 
Dari jumlah kematian tersebut, 85% disebabkan oleh serangan jantung dan stroke. Lebih dari 75& kematian akibat CVDs terjadi di negara
yang berpenghasilan rendah dan menengah. Kebanyakan CVDs bergantung pada kebiasaan dan lingkungan yang menyebabkan beberapa faktor seperti,
merokok, diet tidak sehat, obesitas, kurangnya kegiatan fisik, alkohol, dan polusi udara. Dengan demikian, pentingnya untuk mengetahui CVDs
dengan cepat sehingga bisa berkonsultasi dan merubah gaya hidup yang menjadi lebih sehat.

Di zaman yang sudah penuh dengan teknologi, penyakit dapat diidentifikasi dengan *machine learning*. Menurut paper berjudul "[Comparative Analysis of Heart Disease Prediction Using Logistic Regression, SVM, KNN, and random forest with cross-validation for improved accuracy](https://www.nature.com/articles/s41598-025-93675-1)"
yang tulis oleh Gill S. dkk menerapkan berbagai metode *machine learning* untuk memprediksi risiko penyakit jantung dengan akurasi yang kompetitif. 
Hasil studinya menunjukkan bahwa regresi logistik tetap menjadi metode yang efektif dan populer dalam prediksi penyakit jantung, dengan akurasi yang dapat 
mencapai hingga 88.89% pada beberapa model. Keunggulan metode regresi logistik adalah kemampuannya untuk memberikan interpretasi yang jelas melalui ratio, 
yang sangat berguna dalam konteks medis untuk memahami pengaruh faktor risiko terhadap kejadian penyakit. 

Sebagaimana yang sudah disampaikan, penyakit CVDs penyebab utama kematian global. Penyakit ini bisa dicegah dan diminimalkan dengan deteksi dini dan pengelolaan yang tepat. 
Dengan adanya kematian ini berakibat ke ekonomi yang signifikan, di mana kasus banyak terjadi di negara yang berpenghasilan rendah dan menengah, sehingga ini menjadi tantangan 
besar dalam mengalokasikan sumber daya yang terbatas untuk menangani beban ini. Karena itu diperlukan deteksi atau prediksi yang baik agar dapat menncegah kasus yang akan terjadi. 
Selain itu, dengan teknologi dan metode prediksi menggunakan model regresi logistik diharapkan dapat mengidentifikasi pasien dengan resiko tinggi secara lebih cepat dan akurat. Masalah ini
dapat diselesaikan dengan pengumpulan data dan pengembangan model prediksi yang valid dan interpretatif. 

## Referensi:
- Rimal, Y., Sharma, N., Paudel, S. et al. Comparative analysis of heart disease prediction using logistic regression, SVM, KNN, and random forest with cross-validation for improved accuracy. Sci Rep 15, 13444 (2025). https://doi.org/10.1038/s41598-025-93675-1
- WHO, Cardiovascular diseases (CVDs), https://www.who.int/news-room/fact-sheets/detail/cardiovascular-diseases-(cvds), diakses tanggal 28 Mei 2025.

## Business Understanding

Proses klasifikasi yang dilakukan untuk memprediksi kemungkinan seorang pasien didiagnosis gagal jantung (HeartDisease) berdasarkan dataset yang digunakan.

### Problem Statements
1. Seberapa efektif kita dapat mengidentifikasi pasien yang berisiko tinggi mengalami gagal jantung berdasarkan dataset?
2. Dari semua pasien yang sebenarnya akan mengalami gagal jantung, berapa banyak yang berhasil diidentifikasi oleh model kita?
3. Fitur klinis apa yang paling berpengaruh atau merupakan prediktor terkuat untuk kejadian gagal jantung?
4. Bagaimana kombinasi usia dan kadar gula darah puasa (FastingBS) memengaruhi risiko gagal jantung? Apakah gula darah puasa yang tinggi merupakan faktor risiko yang lebih signifikan pada kelompok usia tertentu?

### Goals
Proyek ini bertujuan untuk mengembangkan pemahaman tentang faktor-faktor yang berkontribusi terhadap penyakit CVDs, serta membangun model prediktif yang dapat diandalkan untuk membantu indentifiksi dini pasien yang beresiko tinggi. 

Solusi yang diberikan:
1. Membangun model klasifikasi dengan mengukur Akurasi Prediksi Keseluruhan
   Menilai kinerja model dalam membuat prediksi yang benar.
2. Memaksimalkan identifikasi kasus positif
   Meningkatkan kasus positif dan mengurangi false negatives pada recall model.
3. Mengidentifikasi faktor risiko utama
   Meningkatkan pemahaman klinis dan memberikan wawasan tentang resiko yang dialami oleh pasien yang meninggal.
4. Menganalisis interaksi fitur
   Mengidentifikasi kelompok berisiko spesifik menurut kelompok umur dengan kadar gula darah puasa (FastingBS)

    ### Solution statements
  
    Solusi yang diberikan sudah menampilkan metrik evaluasi dari model.
   
## Data Understanding
Proyek yang dibuat menggunakan metode regresi logistik dengan menggunakan dataset dari Kaggle berjudul [Heart Failure Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction) yang memiliki 918 data. 

Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

Selanjutnya uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

### Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

## Evaluation
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.
