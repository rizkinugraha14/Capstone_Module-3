# Saudi Arabia Used Cars
### **Contents**

1. Business Problem
2. Data Understanding
3. Data Preprocessing
4. Feature Engineering
5. Modelling
6. Conclusion and Recommendation

## 1. Business Problems

**Context**

Berdasarkan Analisis Pasar Mobil Bekas Saudi Arabia yang didapat dari [Ken Research](https://www.kenresearch.com/white-paper/ksa-used-car-market.php). Pasar Mobil Bekas di Saudi Arabia telah mengalami pertumbuhan positif selama bertahun-tahun didukung oleh peningkatan populasi milenial di negara tersebut seiring dengan masuknya pemain baru ke pasar dengan *growth stage* 2500+ *dealership*. Meningkatnya tren mobil bekas dibandingkan mobil baru menunjukkan preferensi pembeli dalam membeli mobil bekas. Bisnis mobil bekas memiliki persaingan yang ketat,keberhasilan dalam bisnis ini membutuhkan keterampilan dan pengetahuan yang mendalam mengenai mobil. Para pemilik bisnis ini memperoleh mobil bekas yang berkualitas, melakukan perbaikan yang diperlukan, kemudian menjualnya dengan harga yang lebih tinggi. Para pemain ini bersaing berdasarkan parameter seperti *geographical presence*, *value-added services* yang ditawarkan, opsi pembiayaan, *after-sales services* , jaringan *dealership network* dan lainnya

Mobil bekas menjadi pilihan yang menarik karena harganya lebih terjangkau dibandingkan mobil baru. Namun, proses pembelian atau penjualan mobil bekas bisa menjadi tugas yang rumit dikarenakan terdapat banyak jenis mobil (berdasarkan merek, jenis transmisi, ukuran mesin, jarak tempuh, opsi, dan tahun), terutama saat menentukan harga pasar yang terbaik. Banyak orang yang tidak memiliki pengetahuan tentang tren pasar dan membutuhkan metode tepat untuk memberikan perkiraan harga berdasarkan data-data pasar yang tersedia.

**Problem Statement**

Isu utama dalam industri pasar mobil bekas adalah menentukkan harga mobil bekas untuk pembeli atau penjual agar harganya tidak terlalu tinggi untuk konsumen serta tidak terlalu rendah untuk penjual. Penentuan harga mobil bekas berdasarkan merek mobil,tahun, jenis transmisi dan mesin, serta faktor lainnya membutuhkan keahlian profesional yang memahami kondisi mobil dan harga yang sesuai berdasarkan pengalaman sebelumnya. Dalam hal ini, diperlukan sebuah model yang dapat memberikan perkiraan harga mobil bekas berdasarkan data historis yang ada. 

Model tersebut diharapkan memberikan kemudahan bagi pembeli dengan memberikan informasi tentang kualitas mobil, baik itu dalam kondisi yang sangat baik, baik, atau buruk. Di sisi lain, model ini juga dapat membantu para pelaku bisnis mobil bekas dalam menentukan harga jual yang kompetitif.

**Goal**

Sehubungan dengan hal itu, pasar industri mobil bekas memerlukan sebuah model untuk dapat prediksi harga mobil bekas yang dapat diandalkan bagi pengguna yang ingin membeli atau menjual mobil berdasarkan rincian seperti merk mobil, tahun dan jarak tempuh, etc. Sehingga jika seseorang ingin menjual mobilnya, kita dapat memberikan perkiraan harga berdasarkan tren pasar dan sesuai dengan spesifikasi mobil untuk membantu pengguna mengatasi kesulitan dalam menentukan harga yang kompetitif.

**Evaluation Metric**

Evaluasi metrik yang akan kita gunakan adalah  RMSE (Root of Mean Squared Error), MSE (Mean Squared Error), dan MAPE (Mean Absolute Percentage Error) di mana RMSE adalah nilai rataan akar kuadrat dari error, MAE adalah rataan nilai absolut dari error, sedangkan MAPE adalah rataan persentase error yang dihasilkan oleh model regresi. Semakin kecil nilai RMSE, MAE, dan MAPE yang dihasilkan, berarti model semakin akurat dalam memprediksi harga sewa sesuai dengan limitasi fitur yang digunakan. Dan menggunakan nilai R-squared digunakan untuk mengetahui seberapa baik model dapat merepresentasikan varians keseluruhan data. Semakin mendekati 1, maka semakin fit pula modelnya terhadap data observasi. 

## 2. Data Understanding

Proses Data Understanding dan Cleaning merupakan tahap awal dalam pengolahan data yang bertujuan untuk memahami karakteristik dan kualitas data yang dimiliki, serta membersihkannya dari potensi kesalahan atau kekurangan. Langkah-langkah ini sangat penting untuk memastikan data yang digunakan dalam analisis atau model memiliki kualitas yang baik dan dapat diandalkan.

Sebelum melakukan analisa, kita ingin melihat anomali apa saja yang terdapat di dalam dataset kita dan perlu ditangani dalam tahapan *data cleaning*.


## 3. Data Preprocessing

Dataset yang digunakan membutuhkan tahapan *Cleaning* yang bertujuan untuk mendapatkan data yang sudah bersih yang akan dilakukan pada tahapan ini dengan tujuan untuk mendaptkan data yang valid guna pengambilan keputusan

## 4. Feature Engineering

Pada tahapan ini akan dilakukan proses:
1. Scalling,  transformasi terhadap data numerik agar antar variabel memiliki skala yang sama
2. Encoding, agar variable kategorik pada dapat direpresentasikan dalam machine learning

### **Conclusion**

Dalam Capstone Project ini, kita telah membangun sebuah model untuk memprediksi harga mobil bekas dengan beberapa kriteria yang telah ditentukkan di atas, dimana model ini dapat menjadi informasi pendukung yang berguna dalam menentukan harga jual dan beli mobil bekas bagi perusahaan maupun individu yang melakukan transaksi.

- Model terbaik yang digunakan disini adalah XGBoost Regressor.
- Hasil dari model menunjukkan bahwa fitur-fitur yang paling signifikan pengaruhnya adalah Make, Year dan Engine Size. 
- Performa model regresi dievaluasi menggunakan metrik RMSE (Root Mean Square Error), MAE (Mean Absolute Error), MAPE (Mean Absolute Percentage Error) dan R-Squared . Setelah melalui proses hyperparameter tuning, model yang dihasilkan tergolong cukup baik dan linear (XGBoost) dimana menghasilkan nilai small error metric values,(RMSE, MAE, MAPE) dan nilai R2 hampir mendekati 1 (0.8)
- Nilai RMSE memiliki makna bahwa ketika model digunakan untuk memprediksi harga mobil bekas, perkiraan harga rata-ratanya dapat memiliki selisih sekitar 35.639 Riyal (RMSE) atau 17467.6 (MAE) dari harga actual. Sedangkan nilai MAPE yang dihasilkan 0.3 yang menunjukkan error absolut pada Price yang diprediksi oleh model. Semakin kecil nilai MAPE berarti nilai taksiran semakin mendekati nilai sebenarnya.
- Sedangkan nilai R2 sebesar 0.8 berarti hubungan antara variabel dan variabel dependen dengan variabel independen sebesar 80%. Nilai R2 yang tinggi menunjukkan bahwa variabel independen mempunyai pengaruh yang besar terhadap variabel dependen
- Ketika Price more than 200000, distribusi plot mulai irregular. Kita dapat melihat bahwa kadang-kadang kita mempunyai harga yang diprediksi tinggi dan kadang-kadang rendah setelah 200000.

Model yang diperoleh masih memiliki potensi untuk ditingkatkan melalui proses-proses tertentu. Namun, untuk saat ini, kami berasumsi bahwa model sudah mencapai hasil yang diharapkan. Selain itu, dalam proses pembuatan model, diperlukan pengetahuan yang mendalam mengenai industri mobil untuk dapat mengembangkan pengembangan model yang lebih baik lagi.

### **Recommendation**


Hal-hal yang dapat dilakukan untuk mengembangkan model agar lebih baik lagi, seperti:

1. Mengecek prediksi mana saja yang memiliki nilai error yang tinggi, kita dapat mengelompokkan error tersebut ke dalam grup overestimation dan underestimation. Lalu kita bisa mengecek hubungan antara error tersebut dengan tiap variabel independen. Pada akhirnya kita dapat mengetahui sebenarnya variabel mana saja dan aspek apa yang menyebabkan model menghasilkan error yang tinggi, sehingga kita bisa melakukan training ulang.

2. Menambahkan fitur/variabel yang mengkategorikan jenis mobil (Sedan,SUV, dst / mobil klasik non klasik), warna mobil, dan lainnya. Dengan memasukkan fitur ini ke dalam model, kemungkinan besar akan meningkatkan akurasi prediksi harga mobil bekas.

3. Jika tersedia tambahan data yang signifikan, dapat mencoba menggunakan model yang lebih kompleks.

4. Analisis kolinearitas dengan menghitung nilai VIF pada setiap fitur. Diharapkan dapat diperoleh model yang lebih baik dengan menghilangkan fitur-fitur yang berkorelasi.


