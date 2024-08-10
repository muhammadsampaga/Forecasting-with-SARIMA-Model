# Forecasting-with-SARIMA-Model
Forecasting Passenger Demand Utilizing SARIMA Models

Hasil forecasting dari model ini memberikan dasar yang solid untuk perencanaan operasional dan strategi pemasaran perusahaan.

Dengan memproyeksikan lonjakan penumpang pada peak season, perusahaan dapat secara proaktif menyiapkan sumber daya yang diperlukan, seperti staf tambahan atau optimalisasi fasilitas. Selain itu, data ini membantu tim pemasaran dalam menentukan target yang tepat dalam merancang kampanye pemasaran.

Explore Gambaran Besar Dataset

Dataset
Tidak ada Data / Bulan yang kosong


Menambahkan Kolom Baru untuk Menunjukkan Bulan dan Tahun


Data tidak memiliki Missing Value


Data tidak memiliki Duplicated Value


Membuat Data menjadi Format Time Series

EDA (Exploratory data analysis)

LinePlot Data per Tahun

Rata-Rata Jumlah Penumpang per Bulan
Lonjakan jumlah penumpang pada bulan Juli dan Agustus yang kemudian menurun di bulan September bisa disebabkan oleh beberapa faktor umum yang sering terjadi dalam data penumpang.

Berikut kemungkinan penyebabnya:

Liburan Musim Panas:

Di banyak negara, bulan Juli dan Agustus adalah musim liburan sekolah dan universitas. Keluarga dan pelajar sering melakukan perjalanan selama periode ini, yang dapat menyebabkan lonjakan penumpang. Cuti dan Liburan: Banyak orang mengambil cuti atau liburan musim panas, sehingga mempengaruhi jumlah perjalanan dan penumpang. Kegiatan Musiman:

Acara Musiman

Bulan Juli dan Agustus sering kali memiliki banyak acara, festival, dan kegiatan khusus yang menarik wisatawan. Ini juga bisa menjelaskan lonjakan penumpang. Cuaca: Cuaca yang lebih baik di musim panas mungkin mendorong lebih banyak orang untuk bepergian. Mulai Sekolah:

Kembali ke Sekolah: Pada bulan September, banyak sekolah dan universitas mulai kembali aktif, sehingga orang tua dan pelajar yang melakukan perjalanan pada musim panas kembali ke rutinitas mereka. Ini dapat menyebabkan penurunan jumlah penumpang.

Dekomposisi Data Time Series

Dekomposisi Data
Setelah melakukan dekomposisi pada data, saya dapat menyimpulkan bahwa data menunjukkan adanya Trend dan efek musiman (Seasonal Multiplicative). Selain itu, data juga tidak bersifat stasioner.

Membagi Data menjadi Train dan Test Data
Dari total 144 baris data, dilakukan pembagian 70% untuk Train dan 30% untuk Test.


Modelling
ETS (Exponential Smoothing Time Series)
Setelah Melakukan Dekomposisi Data sebelumnya dapat dikatakan data memiliki sifat Seasonal Multiplicative.

Mencoba beberapa Parameter untuk model ETS Holt-Winters :


Trend Multiplicative dan Seasonal Additive

Trend Multiplicative dan Seasonal Multiplicative
Model terbaik untuk metode ETS menggunakan konfigurasi sebagai berikut:

Trend = Additive dan Seasonal = Multiplicative.

dengan RMSE : 27.97


Trend Additive dan Seasonal Multiplicative
SARIMA (Seasonal Autoregressive Integrated Moving Average)

Melihat apakah data bersifat stasioner atau tidak
Melihat ACF DAN PACF dari Data




Dari Analisis Plot ACF dan PACF pada Data, selanjutnya saya dapat menentukan P,D,Q untuk model SARIMA.

Model ARIMA yang optimal untuk data ini kemungkinan adalah ARIMA(1,1,1) atau ARIMA(1,1,2), di mana:

p = 1: Mengindikasikan bahwa data memiliki komponen autoregresi pada lag pertama.
d = 1: Menunjukkan bahwa satu kali differencing sudah cukup untuk membuat data stasioner.
q = 1,2 atau 3: Menunjukkan bahwa terdapat komponen moving average yang kuat pada satu, dua atau tiga lag pertama.
Melakukan Pengujian Pada Beberapa Parameter Model SARIMA
Menggunakan Auto Arima :


Menggunakan For Loop untuk mencari Parameter Model SARIMA Terbaik :



Hasil Iterasi Pencarian Parameter Model SARIMA
Hasil Pencarian Parameter Model SARIMA :


RMSE ETS Model :


Dapat Disimpulkan bahwa Model SARIMA (0,0,1) (1,1,3,12) adalah Parameter Model Terbaik


Melakukan Forecasting Penumpang 2 Tahun Kedepan


Hasil Forecasting 2 Tahun kedepan Menggunakan SARIMA Model

Hasil Forecasting 2 Tahun kedepan Menggunakan SARIMA Model
