# Capstone-Project-Modul-3
Nama : Mario Billy Gunawan <br>
Student ID : JCDSOL-009-022 <br>
Topik : [Saudi Arabia Used Cars Dataset](https://www.kaggle.com/datasets/turkibintalib/saudi-arabia-used-cars-dataset) 
<hr>

## Business Problem Understanding
### Context

Pada saat ini, mobil menjadi salah satu kebutuhan utama bagi masyarakat perkotaan yang memiliki mobilitas tinggi. Mobil dapat memberikan rasa aman, nyaman, dan menghemat waktu bagi penggunanya, terutama apabila tidak ada transportasi umum yang memadai. Dalam memenuhi kebutuhan ini, konsumen tidak hanya tertarik dalam membeli mobil dengan keadaan baru, tetapi juga banyak yang tertarik untuk membeli mobil dalam keadaan bekas. Di negara Arab Saudi, terdapat sebuah platform jual-beli mobil bekas bernama Syarah.com. Pada platform ini, konsumen dapat mencari mobil bekas impian mereka dengan harga yang lebih murah dibandingkan dengan harga membeli mobil yang baru. Rata-rata kondisi dari setiap mobil bekas yang dijualpun juga dalam keadaan baik dan depresiasi harga cenderung tidak terlalu tinggi dibandingkan dengan mobil baru. Syarah.com sebagai platform penyedia jasa jual-beli mobil bekas ingin konsumen mendapatkan pengalaman yang terbaik ketika bertransaksi membeli mobil bekas. Oleh karena itu, Syarah.com menyewa seorang Data Scientist untuk membantu mereka dalam membuat sebuah model bisnis yang dapat memprediksi harga mobil bekas dan bisa menguntungkan kedua belah pihak antara pembeli dan penjual.

Dataset terdiri atas 5624 data mobil bekas yang dikumpulkan dari Syarah.com. Setiap baris mewakili mobil bekas. Informasi lain yang mewakili setiap mobil adalah nama mobil, model mobil, tahun pembuatan, asal mobil, opsi kelengkapan mobil, kapasitas mesin, jenis transmisi, jarak tempuh yang pernah ditempuh mobil, harga berdasarkan wilayah, dan apakah mobil dapat dinegosiasikan. <br>

### Problem Statement
Permasalahan yang dihadapi oleh Syarah.com adalah menentukan model bisnis yang dapat menguntungkan secara finansial untuk perusahaan ini dalam menjual mobil bekas. Tetapi juga memberikan pengalaman yang baik bagi para calon pembeli untuk mendapatkan mobil bekas layak pakai dengan harga yang wajar.

### Goals
Menentukan model bisnis yang dapat memprediksi dan membantu calon pembeli dalam mendapatkan harga yang wajar untuk setiap mobil bekas yang akan dibeli. Tetapi juga memberikan keuntungan bagi sang penjual mobil bekas, yaitu Syarah.com. 

### Analytic Approach
Melakukan analisa data untuk menemukan pola dari fitur-fitur yang ada dan dapat membedakan satu jenis mobil dengan jenis mobil lainnya. Kemudian membuat sebuah model regresi yang dapat membantu perusahaan dalam memprediksi harga jual yang tepat dan juga dapat bermanfaat bagi para calon pembeli dalam mendapatkan harga yang wajar untuk mobil bekas yang ingin mereka beli di Arab Saudi.

### Metric Evaluation
Evaluasi metrik yang akan digunakan dalam membangun model machine learning ini, yaitu:
- R-Square  : Menjelaskan seberapa besar variasi nilai Y yang dapat dijelaskan oleh model.
- RMSE      : Nilai rataan akar kuadrat dari error.
- MAE       : Rataan nilai absolut dari error.
- MAPE      : Rataan persentase error yang dihasilkan oleh suatu model regresi.

Model akan semakin akurat dalam memprediksi harga suatu mobil bekas sesuai dengan limitasi fitur yang dipakai apabila nilai R-Square semakin mendekati nilai 1 dan nilai RMSE, MAE, dan MAPE yang dihasilkan semakin kecil.
<hr>

## Data Understanding
- Dataset berasal dari daftar mobil bekas yang dijual di Arab Saudi via syarah.com.
- Informasi dan spesifikasi mengenai mobil yang dijual di syarah.com diwakili oleh setiap baris data.

**Attributes Information**

| **Attribute** | **Data Type** | **Description** |
| --- | --- | --- |
| Type | Object | Jenis mobil bekas |
| Region | Object | Wilayah dimana mobil bekas ditawarkan untuk dijual |
| Make | Object | Nama perusahaan pembuat mobil bekas |
| Gear_Type | Object | Jenis transmisi yang digunakan mobil bekas (Automatic / Manual) |
| Origin | Object | Asal mobil bekas (Saudi / Gulf Arabic / Other) |
| Options | Object | Opsi kelengkapan mobil bekas (Full / Semi-Full / Standard) |
| Year | Integer | Tahun produksi mobil bekas |
| Engine_Size | Float | Kapasitas mesin mobil bekas |
| Mileage | Integer | Jarak tempuh mobil bekas |
| Negotiable | Boolean | Benar jika harga 0, berarti mobil bekas dapat dinegosiasi |
| Price | Integer | Harga dari mobil bekas |

Atribut Price merupakan target kolom yang akan diprediksi (Dependent Variable) dan kolom-kolom lain merupakan faktor-faktor yang akan mempengaruhi hasil prediksi (Independent Variable).
<hr>

## Conclusion

Berikut ini merupakan beberapa kesimpulan yang dapat diambil dari pembangunan model secara keseluruhan:

- Fitur 'Year' dan 'Engine_Size' memiliki korelasi positif dengan fitur target 'Price', sedangkan fitur 'Mileage' berkorelasi negatif. Untuk fitur kategorikal, fitur 'Type' memiliki korelasi ratio yang paling baik terhadap fitur target 'Price' dibandingkan fitur kategorikal lainnya.
- Terdapat beberapa batasan yang ditetapkan dalam membangun model ini, yaitu:

    1. Mengeliminasi baris dengan isi data yang duplikat sebanyak 4 buah, baris dengan isi data == 0 dan 1 pada fitur 'Price' sebanyak 1796 dan 1 buah. Data-data tersebut harus dieliminasi supaya model yang dibangun dapat memprediksi dengan menggunakan harga yang nyata dan mendapatkan hasil prediksi yang baik, akan tetapi hal tersebut membuat jumlah observasi data menjadi cukup banyak berkurang.
    2. Dalam memprediksi, model menggunakan data fitur 'Year' dengan nilai kurang dari atau sama dengan tahun 2025.
    3. Dalam memprediksi, model menggunakan data fitur 'Engine_Size' dengan nilai kurang dari atau sama dengan 7.
    4. Dalam memprediksi, model menggunakan data fitur 'Mileage' dengan nilai kurang dari 385500 km.
    5. Dalam memprediksi, model menggunakan data fitur 'Price' dengan nilai kurang dari atau sama dengan 183750 Saudi Riyal (SAR).
- Metrik evaluasi yang digunakan dalam pembangunan model ini adalah R-square, RMSE, MAE, dan MAPE. 
    - Nilai R-square menunjukkan seberapa besar pengaruh fitur-fitur (variabel independen) terhadap target (variabel dependen) secara menyeluruh. Jika dilihat nilai R-square yang dihasilkan oleh model XGBoost setelah dilakukan proses tuning hyperparameter lebih tinggi dibandingkan dengan model XGBoost sebelum dilakukan proses tuning hyperparameter. Nilai R-square tersebut adalah 0.632565, artinya fitur dapat menjelaskan 63.25% dari keseluruhan model.
    - Nilai RMSE setelah dilakukan proses tuning hyperparameter adalah sebesar nilai 23757.04, artinya model yang dibangun untuk memprediksi harga mobil bekas di antara rentang harga 0 sampai dengan 183750 SAR, maka harga rata-rata dari prediksi tersebut akan meleset sekitar 23757.04 dari harga aktual. 
    - Harga prediksi tersebut bisa saja meleset lebih jauh lagi apabila dilihat dari nilai MAE dan MAPE yang besar sebelum dilakukan proses tuning hyperparameter. Beruntung nilai RMSE, MAE, dan MAPE dari model mengalami penurunan setelah dilakukan proses tuning hyperparameter. Hal ini menunjukkan bahwa proses tersebut berhasil meningkatkan kinerja model dan dapat membuat prediksi yang lebih baik.
<hr>

## Recommendation

Berikut ini merupakan beberapa rekomendasi yang dapat diberikan dari pembangunan model agar dapat menghasilkan prediksi yang lebih baik:

- Setelah dilakukan proses eliminasi berupa penghapusan baris data dengan nilai == 0 dan 1 SAR pada fitur 'Price', pembatasan nilai pada baris data di fitur 'Year', 'Engine_Size', 'Mileage', dan 'Price' karena adanya outlier, jumlah observasi data yang digunakan untuk pembangunan model hanya tersisa 3.408 baris data atau sekitar 40% dari jumlah pada dataframe awal. Oleh karena itu, untuk pembangunan model selanjutnya disarankan untuk menambahkan jumlah baris data yang akan digunakan, sehingga dapat menghasilkan prediksi yang lebih akurat, karena data yang digunakan pada pembangunan model saat ini sangat sedikit untuk bisa memberikan hasil prediksi yang maksimal.
- Menambahkan beberapa fitur lain yang memiliki korelasi yang baik dengan fitur target 'Price'. Seperti warna mobil, kondisi interior dan eksterior mobil, kelengkapan dokumen (BPKB, STNK, dan Buku Manual), riwayat pemeliharaan mobil, dan riwayat kecelakaan. (Sumber: [What are the factors that influence a used car price?](https://carsellzone.com/blog/detail/factors-affect-car-price))
- Menambahkan fitur yang dapat membedakan antara mobil classic dengan mobil biasa yang digunakan sehari-hari. Hal ini dikarenakan korelasi antara fitur 'Mileage' dengan target 'Price' antara mobil classic dengan mobil biasa memberikan hasil yang berbeda. Contohnya, mobil classic yang diproduksi pada tahun 1970 cenderung akan lebih mahal dibandingkan dengan mobil keluaran tahun 2005. Akan tetapi, untuk mengklasifikasikan hal tersebut diperlukan adanya domain knowledge mengenai jenis mobil apa saja yang dapat dikategorikan ke dalam jenis mobil classic.
