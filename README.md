# **E-COMMERCE CUSTOMER CHURN ANALYSIS & PREDICTION MODEL**

for Purwadhika Final Project | Group Beta JCDSAH-0104

***


### Context:

Tungtungpedia merupakan perusahaan e-commerce yang menjual berbagai macam barang dengan kategori yang beragam. Mulai dari barang elektronik, fashion, bahkan hingga bahan makanan/ kebutuhan dapur. Tungtungpedia hadir sebagai platform yang menjembatani transaksi antara penjual dan pembeli, memberikan solusi belanja online yang cepat, aman, dan efisien untuk memenuhi kebutuhan pelanggan.

Namun demikian, pada era serba digital Tungtungpedia bukanlah satu-satunya e-commerce yang menawarkan solusi ini. Persaingan menuntut perusahaan untuk terus menyesuaikan strategi agar bisa bertahan di pasar yang kompetitif. Mulai dari kualitas layanan hingga retensi pelanggan. Untuk mengetahui strategi paling tepat, sebaiknya dianalisa secara terukur dengan berbasis data agar perusahaan dapat berjalan dengan berkelanjutan dan mampu tumbuh dalam jangka panjang.

Dalam dunia bisnis, menjalankan perusahaan tentu memiliki tantangannya masing-masing. Bagi Tungtungpedia, salah satu tantangan yang dihadapi saat ini adalah retensi pelanggan. Dalam lingkup digital yang sangat dinamis, pelanggan memiliki banyak pilihan dan dapat dengan mudah berpindah ke platform lain dan berhenti menggunakan layanan platform Tungtungpedia.

Pelanggan yang berhenti menggunakan layanan ini dapat disebut sebagai pelanggan **churn**. Mengutip dari sebuah [artikel IBM]('https://www.ibm.com/id-id/think/topics/customer-churn'), "Churn pelanggan adalah jumlah pelanggan lama yang hilang, karena alasan apa pun, selama periode waktu tertentu. Hal ini memberikan pemahaman kepada perusahaan mengenai kepuasan pelanggan dan loyalitas pelanggan, serta dapat mengidentifikasi potensi perubahan pada keuntungan perusahaan".

Untuk menanggulangi tantangan ini secara terukur, diperlukan juga pendekatan prediktif berbasis machine learning. Keunggulan model machine learning adalah dapat mengidentifikasi data kompleks dengan volume besar, dimana akan sangat sulit jika dilihat secara langsung dan analisa manual. Dari data historis yang dimiliki Tungtungpedia, model klasifikasi dapat digunakan untuk mengidentifikasi pola-pola pelanggan yang berpotensi churn sejak dini.


### Classification Characteristic:

Model ini dikembangkan untuk memprediksi apakah seorang nasabah berpotensi untuk melakukan churn (positif) atau tidak (negatif), berdasarkan data historis:
* Kelas Positif (1): Pelanggan melakukan churn.
* Kelas Negatif (0): Pelanggan tidak melakukan churn.

Dengan pendekatan klasifikasi, model akan dibangun, dilatih, dan dievaluasi berdasarkan seberapa baik model bisa membedakan pelanggan yang akan churn atau tidak. Kemudian output dari model dapat dijadikan landasan dalam pembuatan strategi campaign retensi oleh team sales & marketing.

### Problem Statement:

Strategi pemasaran yang tidak ditargetkan secara akurat dapat menyebabkan:
* Efektivitas kampanye yang rendah karena salah sasaran
* Pemborosan anggaran, waktu, dan sumber daya team marketing
* Kehilangan potensi pendapatan akibat churn yang tidak terdeteksi dari awal

Stakeholder utama dari permasalahan ini adalah team sales & marketing, yang bertanggung jawab terhadap campaign retensi pelanggan dan efisiensi anggaran pemasaran.

### Goals:

Berdasarkan permasalahan tersebut, perusahaan ingin memiliki kemampuan untuk bisa memprediksi kemungkinan pengguna yang akan churn atau tidak, sehingga bisa dengan tepat menerapkan strategi marketing untuk mencegah pengguna agar tidak churn. Perusahaan juga ingin mengetahui faktor apa saja yang menyebabkan pengguna churn atau tidak, sehingga dapat membuat strategi marketing yang tepat untuk diberikan kepada pengguna.

Sebagai team data analis & scientist, tugas team disini untuk membantu perusahaan dalam memahami perilaku pengguna, mengidentifikasi pola potensi churn, serta memberikat insight untuk mendukung pengambilan keputusan.

Yang akan dilakukan team:
* Menganalisis data pelanggan e-commerce
* Mengidentifikasi fitur penting dan pola korelasi terhadap churn dari data yang sudah ada
* Membangun model machine learning untuk memprediksi potensi churn
* Memberikan rekomendasi terukur berdasarkan hasil analisis untuk mendukung kampanye retensi dan efisiensi

Team akan menggunakan SMART goals/approach, antara lain:
* S (Specific): Mengidentifikasi pelanggan dengan kemungkinan tinggi churn dan menyusun strategi marketing yang sesuai
* M (Measurable): Mencapai minimal akurasi prediksi machine learning hingga >80%.
* A (Achievable): Menggunakan data historis pelanggan serta membangun model klasifikasi untuk memprediksi churn
* R (Relevant): Relevan untuk meningkatkan efisiensi pemasaran dan mempertahankan pelanggan (retensi)
* T (Time-bound): Implementasi strategi marketing dijadwalkan secepatnya setelah model terbaik didapatkan.

### Evaluation Metrics:
- Type 1 Error : False Positive

  Model memprediksi pengguna churn, padahal tidak churn

Konsekuensi : Strategi marketing yang dilakukan tidak tepat sasaran. Jika hal tersebut terjadi dan diasumsikan biaya untuk retensi sebesar Rp100.000, maka perusahaan perlu mengeluarkan Rp100.000 per orang yang terprediksi.
<br>
<br>
- Type 2 Error : False Negative

  Model memprediksi tidak churn, padahal sebenarnya akan churn

Konsekuensi : Kehilangan pengguna aplikasi. Jika hal tersebut terjadi dan diasumsuikan biaya untuk akuisisi pelanggan ulang sebesar Rp400.000 [sumber](https://www.shopify.com/in/enterprise/blog/lower-customer-acquisition-costs?utm_source=chatgpt.com), maka perusahaan perlu mengeluarkan Rp400.000 per orang yang akan diakuisisi.
<br>
<br>
Berdasarkan dua risiko/konsekuensi tersebut, resiko terbesar adalah kehilangan pengguna (FN). Maka pemilihan metrik yang dirasa sesuai melainkan:
* Recall -> Model yang sensitif menangkap sebanyak mungkin pelanggan yang benar-benar churn
* F1-Score -> menyeimbangkan antar precision dan recall, jadi cocok jika ingin tetap efisien dalam biaya pemasaran (tidak terlalu banyak FP)
***
