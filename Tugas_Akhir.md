## Topik Penelitian
# Prediksi Kesuksesan Film Menggunakan Algoritma Random Forest Classifier Berdasarkan Skor Rating, Anggaran, dan Pendapatan

## Penjelasan Ringkas
Dewasa ini film sudah bagaikan aspek penting dalam kehidupan manusia sebagai salah satu bentuk hiburan atau rehat dari kepenatan. Sebagai salah satu jenis seni yang populer di era ini, film tentu memiliki berbagai macam bentuk reaksi sebagai bentuk apresiasi. Reaksi yang terbentuk ini mampu mempengaruhi individu lain berkat cerita dari mulut ke mulut. Meski begitu, reaksi satu individu dengan yang lainnya dapat berbeda karena pola pikir dan preferensi unik masing-masing. Akibatnya, ditemukan fenomena deviasi dimana pendapatan _Box Office_ tergolong tinggi, dalam artian pendapatan lebih tinggi dibanding anggaran, tetapi skor atau rating yang diberikan penonton tidak cukup bagus. Eksperimen ini berfokus pada penghitungan atau prediksi kesuksesan film yang dipengaruhi oleh tiga faktor, yaitu skor rating, anggaran, dan pendapatan.

## Metode Penelitian
Metode ini memanfaatkan algoritma klasifikasi Random Forest Classifier yang disediakan oleh salah satu _library machine learning_ popular milik Python, yaitu sklearn. _Library_ ini menyediakan alat-alat untuk melakukan _data mining_ dan analisis data. Dataset yang digunakan diambil dari laman web Kaggle dengan judul ‘IMDB movies dataset’. Dataset ini nantinya akan digunakan baik untuk _training_ maupun _testing_.

1. Random Forest

   Random Forest merupakan metode dalam machine learning yang menggunakan konsep ensemble learning dengan membuat banyak pohon keputusan yang bekerja secara independen. Tiap pohon dalam kumpulan tersebut bertugas melakukan prediksi, dan hasil prediksi dari seluruh pohon digabungkan untuk menghasilkan prediksi akhir.
  Random Forest merupakan metode yang dikembangkan dari _Classification and Regression Trees_ (CART), yang pada umumnya menghasilkan suatu _decision tree_. Sebuah _tree_ dalam CART model biasanya tidak cukup mumpuni untuk melakukan analisis _big data_ yang memiliki banyak faktor. Oleh karena itu, dibutuhkan lebih dari satu _tree_ untuk menangani tiap-tiap faktor sehingga didapatkan sebuah ‘hutan’ atau _forest_ yang mampu memberikan hasil prediksi yang lebih akurat. 
  Untuk menghasilkan banyak _tree_, dilakukan teknik pemilihan sampel secara acak atau randomization dan memastikan bahwa untuk tiap _tree_ tidak menggunakan sampel yang sama. _Output_ banyak _tree_ ini disatukan atau diterapkan _aggregation_, dengan cara _voting_ apabila permasalahannya adalah klasifikasi, atau perata-rataan (_averaging_), apabila permasalahannya adalah regresi hingga didapatkan satu _output_

3.	Pemilihan data

  	Terpilihnya dataset ‘IMDB movies dataset’ didasarkan pada alasan bahwa dataset ini menyediakan tiga poin utama yang menjadi fokus sekaligus faktor pembelajaran bagi mesin, yaitu anggaran atau _budget_, pendapatan atau _revenue_, serta skor atau _score_ yang diambil dari basis data IMDB itu sendiri. Jumlah total yaitu sebanyak 10179 data dengan atribut-atribut sebanyak 12 atribut dengan detail sebagai berikut:
a.	names: Judul film dalam Bahasa Inggris
b.	date_x: Tanggal rilis film 
c.	score: Skor atau rating IMDb
d.	genre: Kategori film
e.	overview: Sinopsis film
f.	crew: Pemain dan kru-kru penting dari film
g.	orig_title: Judul asli (apabila film adalah _non-English_)
h.	status: Status film, apakah sudah atau masih berada di tahap pra-produksi
i.	orig_lang: Bahasa asli film (apabila film adalah _non-English_)
j.	budget_x: Anggaran total yang dikeluarkan
k.	revenue: Pendapatan _Box Office_
l.	country: Negara asal film 

4.	Pre-processing Data
   
   Proses ini dilakukan agar dataset tidak menghambat proses pembelajaran algoritma. Proses yang diterapkan dalam eksperimen ini adalah penghapusan nilai _null_. Pada kasus dataset ini, ditemukan bahwa ada banyak detail data yang terpisah _cell_ sehingga dianggap tidak lengkap atau _null_. Dari 10179, terdapat 162 _cell_ dengan data yang tidak lengkap, sehingga jumlah total akhir dataset adalah 10017 baris data. Perbandingan sampling untuk _data training_ dan _testing_ yaitu sebesar 80:20.

## Referensi
[Perbandingan Metode Klasifikasi Random Forest dan SVM Pada Analisis Sentimen PSBB](https://www.researchgate.net/publication/352278601_Perbandingan_Metode_Klasifikasi_Random_Forest_dan_SVM_Pada_Analisis_Sentimen_PSBB)

[Prediksi Rating Film Menggunakan Metode Naïve Bayes](https://www.researchgate.net/publication/314356915_Prediksi_Rating_Film_Menggunakan_Metode_Naive_Bayes)

[Random Forest](https://meridian.allenpress.com/jim/article/47/1/31/131479/Random-Forest)

## Dataset
[IMDB movies dataset (kaggle.com)](https://www.kaggle.com/datasets/ashpalsingh1525/imdb-movies-dataset)

## Analisis
Didapatkan confusion matrix sebagai berikut: 

![image](https://github.com/claradivap512/riset-informatika/assets/112915547/5404b72d-ad98-4fb6-9040-61513e2da9b9)

Angka 0 dan 1 merujuk pada kategori hasil kesuksesan film, dimana 0 merepresentasikan "tidak sukses" dan 1 merepresentasikan "sukses". Dari 2036 data atau 20% dari data total, terhitung ada sebanyak 987 film yang tergolong tidak sukses dan 1049 film yang tergolong sukses.

Dengan tingkat akurasi 98%, membuktikan bahwa performa model cukup mendekati akurasi level tinggi dan cocok digunakan untuk dataset ini.
