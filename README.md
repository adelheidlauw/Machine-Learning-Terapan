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
Proyek yang dibuat menggunakan metode regresi logistik dengan menggunakan dataset dari Kaggle berjudul [Heart Failure Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction). Dataset ini memiliki 918 data dengan 7 kolom numerik dan 5 kolom kategorikal.

### Variabel-variabel pada Heart Failure Prediction dataset adalah sebagai berikut:
- Age : Umur dari pasien [years]
- Sex : Jenis kelamin [M: Male, F: Female]
- ChestPainType : Tipe Nyeri Dada [TA: Typical Angina, ATA: Atypical Angina, NAP: Non-Anginal Pain, ASY: Asymptomatic]
- RestingBP : Tekanan darah [mm Hg]
- Cholesterol : Kolestrol serum [mm/dl]
- FastingBS : Gula darah puasa [1: jika puasa gula darahnnya>120mg/dl, 0: lainnya]
- RestingECG : Hasil elektrokardiogram istirahat [Normal: Normal, ST: memiliki kelainan gelombang ST-T (gelombang T inversi dan/atau ST eleavasi atau depresi > 0.05 mV), LVH: menampilkan hipertrofi ventrikel kiri yang mungkin atau pasti menurut kriteria Estes]
- MaxHR : Detak jantung maksimum yang dicapai [bernilai numerik antara 60 dan 202]
- ExerciseAngina : Latihan induksi angina [Y:Iya, N: Tidak]
- Oldpeak : oldpeak = ST [bernilai numerik yang mengukur ketika depresi]
- ST_Slope : Kemiringan dari puncak latihan segmen ST
- HeartDisease : Hasil output kelas [1:penyakit jantung, 0: normal]

### Exploratory Data Analysis (EDA)
Untuk memahami dataset yang digunakan dilakukan:
- Distribusi variabel target (HeartDisease)
  Melihat seberapa seimbang kelas target. 
- Visualisasi data
  Menampilkan histogram, barplot, confusion matrix dari data-data numerik dan kategorikal, serta mengecek relevansi penyakit jantung dengan faktor lainnya

## Data Preparation
Persiapan data yang dilakukan: 
- Mengecek informasi singkat dan statistika dataset
  Dilakukan dengan menggunakan `.head()`,`.info()` dan `.describe()` agar memudahkan saat melakukan pemrosesan data
- Mengecek adanya *missing value*
  Mengevaluasi jumlah data yang memiliki data kosong atau NaN di setiap kolomnya agar tidak menghasilkan prediksi yang salah dengan `.isnull().sum()`.
- Identifikasi Fitur dan Target
  Kolom HeartDisease diidentifikasi sebagai variabel target (y) dan sisanya akan digunakan sebagai variabel prediktor (X).
- Pembagian data (*training* dan *testing set*)
  Dibagi menjadi 80% *training* dan 20% *testing* dan menggunakan parameter `stratify=y` untuk memastikan proporsi kelas target di data *training* dan *testing* sama. Selain itu, pembagian ini untuk mencegah *overfitting* pada data *testing*.
- Preprocessing fitur
  Dilakukan transform kolom dengan `StandardScaler` untuk kolom numerik sehingga memiliki rata-rata 0 dan standar deviasi 1. Fitur ini mencegah adanya dominasi perhitungan jarak atau bobot model dibandingkan fitur dengan rentang kecil sepertti pada variabel Sex yang memiliki nilai 0 atau 1. Digunakan juga One-Hot Encoding untuk kolom kategorikal menjadi kolom biner dengan parameter `handle_unkwown='ignore'` untuk menangani kategori yang mungkin muncul di data *testing* tetapi tidak ada di data *training*.

   ### Hasil Dari Data Preparation
  ```
  File yang berhasil diekstrak:
   ['.config', 'heart.csv', 'heart-failure-prediction.zip', 'sample_data']
   Age Sex ChestPainType  RestingBP  Cholesterol  FastingBS RestingECG  MaxHR  \
   0   40   M           ATA        140          289          0     Normal    172   
   1   49   F           NAP        160          180          0     Normal    156   
   2   37   M           ATA        130          283          0         ST     98   
   3   48   F           ASY        138          214          0     Normal    108   
   4   54   M           NAP        150          195          0     Normal    122   

  ExerciseAngina  Oldpeak ST_Slope  HeartDisease  
   0              N      0.0       Up             0  
   1              N      1.0     Flat             1  
   2              N      0.0       Up             0  
   3              Y      1.5     Flat             1  
   4              N      0.0       Up             0  
   ```
  Hasil dari 5 baris pertama dataset yang digunakan dengan perintah `.head()`.
   ```
   <class 'pandas.core.frame.DataFrame'>
   RangeIndex: 918 entries, 0 to 917
   Data columns (total 12 columns):
    #   Column          Non-Null Count  Dtype  
   ---  ------          --------------  -----  
    0   Age             918 non-null    int64  
    1   Sex             918 non-null    object 
    2   ChestPainType   918 non-null    object 
    3   RestingBP       918 non-null    int64  
    4   Cholesterol     918 non-null    int64  
    5   FastingBS       918 non-null    int64  
    6   RestingECG      918 non-null    object 
    7   MaxHR           918 non-null    int64  
    8   ExerciseAngina  918 non-null    object 
    9   Oldpeak         918 non-null    float64
    10  ST_Slope        918 non-null    object 
    11  HeartDisease    918 non-null    int64  
   dtypes: float64(1), int64(6), object(5)
   memory usage: 86.2+ KB
   None
   ```
   Terdapat 918 baris kolom dengan tipe dari setiap variabelnya menggunakan `.info()`.
   ```
            Age   RestingBP  Cholesterol   FastingBS       MaxHR  \
   count  918.000000  918.000000   918.000000  918.000000  918.000000   
   mean    53.510893  132.396514   198.799564    0.233115  136.809368   
   std      9.432617   18.514154   109.384145    0.423046   25.460334   
   min     28.000000    0.000000     0.000000    0.000000   60.000000   
   25%     47.000000  120.000000   173.250000    0.000000  120.000000   
   50%     54.000000  130.000000   223.000000    0.000000  138.000000   
   75%     60.000000  140.000000   267.000000    0.000000  156.000000   
   max     77.000000  200.000000   603.000000    1.000000  202.000000   

          Oldpeak  HeartDisease  
   count  918.000000    918.000000  
   mean     0.887364      0.553377  
   std      1.066570      0.497414  
   min     -2.600000      0.000000  
   25%      0.000000      0.000000  
   50%      0.600000      1.000000  
   75%      1.500000      1.000000  
   max      6.200000      1.000000  
   ```
   Tabel statistika deskriptif untuk mempermudah melihat nilai-nilai pada kolom numerik. Pada variabel RestingBP dan Cholesterol, nilai minimumnya 0 sehingga data ini harus dicek kembali. 
   ```
   Jumlah nilai NaN di setiap kolom:
   Age               0
   Sex               0
   ChestPainType     0
   RestingBP         0
   Cholesterol       0
   FastingBS         0
   RestingECG        0
   MaxHR             0
   ExerciseAngina    0
   Oldpeak           0
   ST_Slope          0
   HeartDisease      0
   dtype: int64
   ```
   Tidak ada variabel yang memiliki kolom kosong.
  
## Modeling
Setelah data disiapkan dan dipahami melalui EDA, lengkah berikutnya adalah membangun model yang mampu mempelajari pola dari data *training* dan membuat prediksi akurat pada data baru. Pada proyek ini, model yang digunakan adalah regresi logistik yang menjadi algoritma klasifikasi. Algoritma ini digunakan untuk memprediksi probabilitas hasil biner, misalnya 0 titik gagal jantung dan 1 gagal jantung.
- Kelebihan Regresi Logistik:
   - Sederhana dan cepat
   - Menghasilkan *output* probabilitas
   - Efektif untuk data yang dapat dipisahkan secara linier
- Kekurangan Regresi Logistik:
   - Asumsi linieritas, memungkinkan model bekerja tidak optimal
   - Sensitif terhadap fitur yang tidak relevan
   - Kurang baik untuk data yang hubungan kompleks

### Tahapan Modeling
1. Pelatihan Model Regresi Logistik
   - Inisialisasi model `LogisticRegression`
   - Pelatihan model `model.fit()`, dilatih menggunakan data *training* yang sudah diskalakan (`X_train_scaled`) dan variabel target yang sesuai (`y_train`). Proses pelatihan ini untuk meminimalkan fungsi loss dan memprediksi probabilitas HeartDisease. Parameter yang digunakan `random_state=42` untuk melakukan pengambilan acak dan `solver=`liblinear`` untuk optimasi, menemukan bobot koefisien terbaik.
2. Prediksi
   - Setelah model berhasil dilatih, `model.predict()` akan digunakan untuk membuat prediksi pada data *testing* yang sudah diskalakan (`X_test_scaled`). Model ini akan menghasilkan *output* biner (0 atau 1) yang mewakili prediksi apakah pasien akan mengalami gagal jantung atau tidak.
3. Merubah variabel target menjadi FastingBS untuk menjawab pertanyaan bisnis keempat untuk melakukan analisis interaksi antarfitur.

## Evaluation
Setelah model berhasil dilatih, selanjutnya dilakukan evaluasi kinerja model. Metrik evaluasi dapat membantu kita memahami seberapa baik model dalam memprediksi HeartDisease dan menjawab pertanyaan-pertanyaan bisnis yang telat ditetapkan. Dalam proyek ini, digunakan akurasi, *confusion matrix*, recall, dan F1-Score. Metrik-metrik ini dipilih karena sangat relevan untuk masalah klasifikasi biner yang di mana identifikasi positif dan meminimalisasi kesalahan dengan konsekuensi penting.
- Akurasi (*Accuracy Score*)
- Recall
- 
Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.
