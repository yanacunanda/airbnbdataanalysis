# **Analisis Performa Listing Airbnb Bangkok**

## **Latar Belakang, Permasalahan, dan Tujuan**
Airbnb sebagai perusahaan terkemuka dalam penyediaan layanan penyewaan penginapan
(berupa villa, rumah, apartment, dan kamar hotel) di seluruh dunia dengan ribuan listing
yang tersebut di 100.000 kota di berbagai negara. Airbnb juga memiliki kehadiran yang
signnifikan di Kota Bangkok, Thailand. **Saat ini, Airbnb Bangkok merasa penting untuk melakukan evaluasi menyeluruh terhadap performa berbagai listing yang ada di bawah payungnya.**

Tujuan dari evaluasi ini adalah untuk mengidentifikasi aspek-aspek tertentu yang mungkin memerlukan optimalisasi atau peningkatan. Dalam konteks ini, beberapa parameter kunci yang menjadi fokus analisis meliputi: 

- Pengaruh kategori distrik terhadap jumlah listing yang diminati
- Identifikasi 10 distrik teratas berdasarkan jumlah listing
- Persentase listing yang telah menerima review dari tamu
- Tingkat ketersediaan listing
- Identifikasi pemilik listing yang memiliki lebih dari satu listing terdaftar

Hasil dari analisis ini akan memberikan wawasan berharga kepada **Divisi Pengembangan Produk Airbnb Bangkok** untuk membantu mereka mengambil keputusan yang lebih cerdas dan berfokus pada perbaikan layanan yang akan meningkatkan pengalaman bagi para tamu dan pemilik listing di Kota Bangkok

## **Pemahaman Tentang Data yang Digunakan**

Dataset yang digunakan adalah: Airbnb Listings Bangkok.csv

Dataset ini memuat beragam informasi terkait setiap properti yang terdaftar sebagai listing di Airbnb Bangkok. Dalam dataset ini terdapat 17 kolom yang mengandung berbagai informasi yang relevan.

|Nama Kolom| Deskripsi|
|-----------|------|
|id|Angka unik untuk mengidentifikasi listing|
|name|Nama listing|
|host_id|Angka unik untuk mengidentifikasi pemilik listing (host)|
|host_name|Nama host|
|neighbourhood|Lokasi distrik dari setiap listing (ditentukan berdasarkan titik koordinat)|
|latitude|Titik lintang|
|longitude|Titik bujur|
|room_type|Jenis listing (entire home/apt, private room, shared room, dan hotel room)|
|price|Harga listing (per malam)|
|minimum_nights|Jumlah minimum malam yang diperlukan untuk menginap|
|number_of_reviews|Jumlah review|
|last_review|Tanggal review terakhir|
|calculated_host_listings_count|Jumlah listing yang dimiliki oleh host|
|availability_365|Jumlah hari availability|
|number_of_reviews_ltm|Jumlah review selama 12 bulan ke belakang|
  
Selain itu terdapat penambahan kolom ke dalam dataset untuk mendukung analisis yang akan dilakukan, yaitu:

|Nama Kolom|Deskripsi|
|-----------|------|
|neighbourhood_category|Kategori distrik (Tourist Area, Shopping Area, Entertainment Area, Resident Area, dan Other)|
|review|Keterangan mengenai listing sudah mendapatkan review atau belum|

Berikut ini adalah penjelasan mengenai detail kolom room_type:

|room_type|Deskripsi|
|-----------|------|
|entire home/apt|Jenis listing yang menyewakan seluruh bangunan untuk tamu. Biasanya ini termasuk sebuah kamar tidur, sebuah kamar mandi, sebuah dapur, dan sebuah pintu masuk yang terpisah dan khusus.|
|private room|Jenis listing yang menyewakan kamar tidur pribadi untuk tidur dan mungkin akan berbagi beberapa ruang dengan orang lain.|
|shared room|Jenis listing yang menyewakan kamar tidur dan ruangan lainnya dengan berbagi bersama orang lain.|
|hotel room|Jenis listing yang menyewakan sebuah kamar tidur di sebuah hotel.|

Berikut ini adalah penjelasan mengenai detail kolom neighbourhood_category:

|neighbourhood_category|Deskripsi|
|-----------|------|
|Tourist Area|Distrik yang terdapat tempat wisata terkenal|
|Shopping Area|Distrik yang terdapat mall/shopping center besar|
|Entertainment Area|Distrik yang terdapat pub, nightclub, night streetfood|
|Resident Area|Distrik yang ditujukan untuk area tempat tinggal|
|Other|Distrik-distrik selain kategori di atas (multipurpose area, industy area, airport area, military area, commercial area, dan unknown)|

## **Data Cleaning**
Berikut adalah tahapan data cleaning yang akan dilakukan pada dataset ini:
- Mengatasi missing value
    - Mengisi missing value pada kolom 'name'
    - Mengisi missing value pada kolom 'host_name'
    - Mengisi missing value pada kolom 'last_review'
    - Mengisi missing value pada kolom 'reviews_per_month'
- Memeriksa duplikasi data
- Memperbaiki penulisan nama-nama distik
- Memeriksa distribusi data dan outliers
- Menghapus kolom yang tidak diperlukan
- Menambah kolom
    - Menambahkan kolom 'neighbourhood_category'
    - Menambahkan kolom 'review'
- Menampilkan dan menyimpan hasil data cleaning

Data yang telah dibersihkan disimpan dalam file Airbnb-Clean-Fix.csv

## **Kesimpulan**
Berdasarkan analisis yang telah dilakukan, diperoleh kesimpulan-kesimpulan berikut ini:
1. Secara keseluruhan, Other Area memiliki jumlah listing terbanyak. Namun ketika memecah data lebih lancut, dapat dilihat bahwa preferensi jenis listing bervariasi di antara berbagai kategori area. Secara khusus, di Shopping Area, Entertainment Area, dan Resident area, jenis listing yang entire home/apartment merupakan yang paling diminati. Sementara itu, di Tourist Area lebih banyak ditemukan jenis listing private room. Hal ini menunjukkan bahwa setiap area memiliki preferensi yang berbeda dalam hal jenis listing yang mereka cari.
2. Distrik Vadhana, Khlong Toei, Huai Khwang, Ratchathewi, Bang Rak, Sathon, Phra Nakhon, Phra Khanong, Chatu Chak, Bang Na menjadi distrik-distrik dengan jumlah listing terbanyak. Ini bisa menjadi indikasi bahwa distrik-distrik tersebut sangat diminati oleh pemilik listing untuk memperoleh profit dan pengguna Airbnb karena distrik-distrik tersebut menarik untuk menjadi destinasi.
3. Secara keseluruhan, tourist area dan shopping area mendominasi dari segi harga. Hal ini dapat menunjukkan bahwa harga sewa akan dipengaruhi oleh tingkat keramaian lokasinya.
4. Terdapat 37% listing yang belum menerima review. Hal ini berpotensi mempengaruhi tingkat pemesanan (booking rate) untuk listing-listing tersebut karena pengguna cenderung lebih memilih listing yang telah mendapatkan review.
5. Review juga berdampak pada tingkat ketersediaan listing.
6. Terdapat 525 host yang memiliki lebih dari satu listing yang terdaftar dengan kondisi belum pernah mendapatkan ulasan pada listing-listing mereka. Hal ini sebaiknya menjadi perhatian serius bagi Airbnb.

##**Rekomendasi**
Berdasarkan analisis yang telah Anda lakukan, terdapat beberapa rekomendasi yang dapat diimplementasikan oleh Airbnb untuk meningkatkan kinerja dan pengalaman pengguna di Bangkok:

1. **Segmentasi Pasar dan Penawaran Khusus:** Airbnb dapat mengambil keuntungan dari preferensi berbeda dalam jenis listing di berbagai kategori area. Misalnya, Airbnb dapat mengembangkan penawaran khusus untuk mempromosikan listing jenis entire home/apartment di Shopping Area, Entertainment Area, dan Resident Area. Ini dapat mencakup penawaran harga khusus, promosi, atau fitur tambahan yang relevan.
2. **Fokus pada Distrik Populer:** Airbnb bisa bekerja sama dengan pemilik listing di distrik-distrik yang paling diminati, seperti Vadhana, Khlong Toei, dan lainnya. Ini dapat dilakukan dengan memberikan dukungan tambahan dalam hal pemasaran, perbaikan fasilitas, atau insentif bagi pemilik listing untuk menjaga kualitas layanan mereka.
3. **Penetapan Harga yang Lebih Tepat:** Mengingat bahwa tourist area dan shopping area mendominasi dari segi harga, Airbnb dapat memberikan panduan harga yang lebih terperinci kepada pemilik listing. Ini dapat membantu pemilik listing untuk menetapkan harga yang lebih kompetitif dan menarik bagi calon tamu.
4. **Stimulasi Review:** Airbnb harus mendorong pengguna untuk meninggalkan ulasan setelah menginap. Hal ini dapat dilakukan dengan memberikan insentif, seperti poin reward kepada pengguna yang memberikan ulasan. Dengan lebih banyak ulasan, listing akan menjadi lebih menarik bagi calon tamu.
5. **Perbaikan Dukungan untuk Host:** Airbnb perlu memperhatikan host yang memiliki listing dengan kondisi belum pernah mendapatkan ulasan. Mungkin ada alasan mengapa mereka belum mendapatkan ulasan, seperti masalah kualitas atau pemasaran. Airbnb bisa menawarkan pelatihan atau bantuan untuk membantu host meningkatkan kualitas listing mereka dan mendapatkan ulasan positif.
6. **Analisis Ketersediaan Listing:** Airbnb dapat menggunakan data ketersediaan listing untuk membantu host mengoptimalkan tingkat pemesanan. Dengan menganalisis tren dan pola pemesanan, Airbnb dapat memberikan rekomendasi kepada host tentang cara menghindari kekosongan yang tidak perlu.
7. **Pengembangan Fitur Lokal:** Airbnb dapat mengembangkan fitur khusus. Misalnya, panduan wisata lokal, rekomendasi restoran, atau informasi penting tentang lingkungan sekitar listing. Hal ini dapat meningkatkan pengalaman tamu dan membuat mereka lebih cenderung memberikan ulasan positif.

Rekomendasi di atas dapat membantu Airbnb meningkatkan pengalaman pengguna, meningkatkan jumlah pemesanan dan menjaga hubungan yang baik dengan host. Dengan perencanaan dan pelaksanaan yang tepat, Airbnb dapat memaksimalkan potensi pasar di kota ini.

## **Visualisasi Menggunakan Tableau**
Hasil visualisasi pada tableau dapat dilihat pada link berikut ini:

https://public.tableau.com/app/profile/yana.cunanda/viz/CapstoneModule2_16947528337320/HasilVisualisasi?publish=yes
