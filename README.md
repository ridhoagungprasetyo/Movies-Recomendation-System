# Movies-Recomendation-System
Proyek ini  adalah submission pada modul belajar machine learning terapan

# Laporan Proyek Machine Learning System Movies Recomendation- Ridho Agung Prasetyo

## Project Overview

Dalam era digital, informasi yang melimpah menjadi salah satu tantangan utama bagi pengguna dalam membuat keputusan yang tepat. Di bidang hiburan, seperti film, banyaknya pilihan yang tersedia sering kali membuat pengguna bingung memilih tontonan yang sesuai dengan preferensi mereka. Situasi ini menimbulkan kebutuhan akan sistem yang dapat menyaring informasi dan memberikan rekomendasi yang relevan berdasarkan kebutuhan dan minat pengguna. Sistem rekomendasi hadir sebagai solusi yang efektif untuk mengatasi tantangan ini, memainkan peran penting dalam meningkatkan pengalaman pengguna.

Sistem rekomendasi telah menjadi elemen utama dalam berbagai platform layanan digital seperti Netflix, Amazon Prime, dan Disney+. Sistem ini memungkinkan platform untuk mempelajari preferensi pengguna melalui data historis, perilaku, dan informasi kontekstual lainnya. Dengan memberikan rekomendasi yang dipersonalisasi, sistem ini tidak hanya meningkatkan kenyamanan pengguna tetapi juga mendukung keberlangsungan bisnis melalui peningkatan waktu tonton dan loyalitas pengguna.

Teknologi yang mendasari sistem rekomendasi terus berkembang, dengan berbagai pendekatan seperti content-based filtering, collaborative filtering, dan model berbasis pembelajaran mendalam. Masing-masing pendekatan memiliki keunggulan dan kelemahan yang berbeda. Dalam proyek ini, pendekatan content-based filtering dipilih karena kesederhanaan dan efektivitasnya dalam situasi di mana data deskriptif tentang item, seperti genre dan deskripsi film, tersedia dalam jumlah yang memadai. Metode ini memungkinkan sistem untuk memahami hubungan antara fitur-fitur tertentu dan preferensi pengguna.

Peningkatan minat terhadap sistem rekomendasi tidak hanya didorong oleh kebutuhan pengguna tetapi juga oleh kemampuan teknologi untuk memproses data besar dalam waktu singkat. Dengan adanya teknik analisis data seperti pemrosesan teks dan penghitungan kesamaan vektor, sistem rekomendasi dapat memberikan hasil yang cepat dan akurat. Sebagai contoh, perhitungan kesamaan antarfilm berdasarkan genre atau deskripsi dapat membantu menemukan film yang relevan tanpa memerlukan data interaksi pengguna yang besar.

Proyek ini bertujuan untuk membangun sistem rekomendasi film menggunakan pendekatan content-based filtering dengan memanfaatkan data film seperti genre, deskripsi, dan atribut lainnya. Dengan solusi ini, diharapkan sistem dapat memberikan rekomendasi film yang relevan, meningkatkan kepuasan pengguna, dan menjadi dasar untuk pengembangan lebih lanjut menuju model rekomendasi yang lebih kompleks. Proyek ini juga berkontribusi dalam mempelajari bagaimana pendekatan sederhana seperti content-based filtering dapat dioptimalkan untuk memenuhi kebutuhan pengguna dalam konteks hiburan digital.

Sistem rekomendasi film memiliki dampak signifikan dalam meningkatkan pengalaman pengguna di era digital. Proyek ini penting karena menyelesaikannya akan memberikan solusi praktis terhadap tantangan dalam memilih konten yang relevan di tengah banyaknya pilihan film. Pengguna sering kali menghadapi information overload, yang dapat mengurangi kepuasan mereka terhadap layanan hiburan digital. Dengan membangun sistem rekomendasi yang efektif, pengalaman pengguna dapat ditingkatkan, yang pada gilirannya mendukung keberlanjutan bisnis penyedia platform.

Sebuah laporan dari [1](https://www.mckinsey.com/)McKinsey & Company (2013)  mencatat bahwa rekomendasi personalisasi dapat meningkatkan pendapatan hingga 20-30% pada platform digital karena pengguna cenderung menghabiskan lebih banyak waktu dan melakukan pembelian tambahan ketika rekomendasi relevan dengan kebutuhan mereka. Dalam konteks layanan streaming seperti Netflix, hingga 80% film yang ditonton pengguna berasal dari rekomendasi algoritma mereka, menunjukkan pentingnya sistem rekomendasi dalam menarik perhatian pengguna dan meningkatkan keterlibatan mereka dengan platform [2](https://dblp.org/rec/journals/tmis/Gomez-UribeH16.html)(Gomez-Uribe & Hunt, 2015) .

Penelitian lain oleh [4](https://www.sciencedirect.com/)Sharma dan Garg (2020) dalam jurnal International Journal of Information Management menunjukkan bahwa sistem rekomendasi berbasis konten (content-based filtering) memberikan keunggulan dalam memahami atribut produk seperti genre atau deskripsi film, yang penting untuk memberikan rekomendasi yang akurat. Hal ini menunjukkan bahwa pendekatan seperti yang diterapkan dalam proyek ini tidak hanya relevan tetapi juga memiliki basis ilmiah yang kuat untuk diterapkan pada kasus nyata.

Selain manfaat bagi pengguna, keberhasilan proyek ini juga membuka peluang pengembangan sistem rekomendasi lebih lanjut. Sistem berbasis content-based filtering yang diusulkan dapat menjadi dasar untuk mengintegrasikan pendekatan lain seperti collaborative filtering atau model berbasis pembelajaran mendalam (deep learning). Dengan demikian, proyek ini dapat menjadi langkah awal dalam pengembangan teknologi rekomendasi yang lebih canggih.

Pentingnya sistem rekomendasi juga didukung oleh laporan akademik [3](https://link.springer.com/)Ricci, Rokach, dan Shapira (2015), yang menjelaskan bahwa personalisasi melalui algoritma tidak hanya meningkatkan kepuasan pengguna tetapi juga membantu penyedia layanan memahami preferensi pasar. Hal ini sangat relevan untuk industri film yang terus berkembang dengan dinamika preferensi pengguna yang kompleks.

Dengan dasar riset yang kuat dan manfaat praktis yang signifikan, penyelesaian proyek ini menjadi esensial untuk memajukan solusi teknologi rekomendasi di sektor hiburan digital.

## Business Understanding
### Problem Statements
- Bagaimana cara melakukan pra-pemrosesan pada data movie recomendation yang akan digunakan agar dapat membuat model yang baik menggunakan teknik content-base filtering?
- Bagaimana memberikan rekomendasi judul film berdasarkan genre pada setiap judul film yang pelanggan input sehingga dapat memberikan preferensi yang sesuai pelanggan inginkan?

### Goals
- Melakukan pra-pemrosesan dengan baik agar dapat digunakan dalam pembuatan model.
- Membuat pelanggan lebih mudah menemukan judul film yang tepat dengan bantuan sistem rekomendasi judul film berdasarkan genre yang dibuat.

Untuk mencapai tujuan dari proyek ini dilakukan langkah-langlkah sebagai berikut:
- Analisis data mentah, termasuk memahami atribut yang tersedia (misalnya: ID film, judul, genre).
- Menghapus data duplikat, menangani nilai yang hilang, dan menghapus data yang tidak relevan.
- Ekstrasksi fitur dengan menggunakan Count Vectorizer untuk mempresentasikan genre dalam bentuk numerik.
- Metode yang digunakan pada projek ini adalah Content-Based Filtering. Content-Based Filtering adalah rekomendasi berbasis konten yang merekomendasikan item yang memiliki kemiripan dengan item yang disukai/diinput pengguna sebelumnya. Content-based filtering mempelajari profil minat pengguna baru berdasarkan data dari objek yang telah dinilai pengguna. Metode ini bekerja dengan menyarankan item serupa yang pernah disukai sebelumnya atau sedang dilihat sekarang kepada pengguna berdasrakan kategori tertentu dari item yang dinilai oleh pengguna.
    
    Kelebihan dan Kekurangan dari Content-based Filtering adalah sebagai berikut:
    * Kelebihan
        * User Independence
        Tidak bergantung kepada user lain dalam memberikan rekomendasi yang ada. New Item Mampu merekomendasikan item yang belum dinilai oleh setiap pengguna.
    * Kekurangan
        * New User
        Sistem tidak dapat memberikan rekomendasi yang dapat diandalkan pada pengguna baru, karena membutuhkan penelusuran terlebih dahulu pada preferensi pengguna.

## Data Understanding
Dataset yang digunakan dalam proyek system recomendation ini dalah dataset movies.csv yang didapatkan/diunduh dari kaggle [Kaggle Dataset : Movie recomendation pjct](https://www.kaggle.com/datasets/sayan0211/movie-recomendation-pjct).
Dataset ini memiliki total jumlah baris 9742 dan terdapat 3 kolom yaitu movieId, title, dan genres. Dataset ini berisi film-film yang sering ditonton oleh banyak masyarakat luas. Dalam Datase ini sudah tidak ada data duplikat dan sudah tidak ada missing value dalam data. Sehingga dataset bisa langsung kita gunakan untuk membuat sistem rekomendasi.

Variabel-variabel pada movies dataset adalah sebagai berikut:
- movieId : merupakan parameter bernilai unique. Parameter ini digunakan utk mengindetifikasi daftar tiap-tiap film.
- title : merupakan parameter yg menyimpan judul masing-masing film.
- genres : parameter yg menyimpan tiap-tiap kategori film.

Untuk memahami dataset beberapa langkah yang dilakukan sebagai berikut:
- Menampilkan jumlah baris dan kolom pada data,![14](https://github.com/user-attachments/assets/320530f1-5755-4265-b704-6fe38c27f1c0)
- Memeriksa tipe variabel beserta jumlahnya,![13](https://github.com/user-attachments/assets/34e2d204-97f0-4228-895b-798b520e8b06)
- Melihat statistik deskriptif dari data,![12](https://github.com/user-attachments/assets/d14c775e-a514-4550-a7f1-833850ba308e)
- Menghitung jumlah data genre uniqe dalam data.![11](https://github.com/user-attachments/assets/b6b97af3-a19d-495c-8b1e-64184cd02379)

## Data Preparation
Berikut adalah tahapan-tahapan dalam melakukan Persiapan data:
1. Memuat dataset ke variabel baru dan mengurutkan ulang data (tranformasi data). 
![8](https://github.com/user-attachments/assets/00acb015-f39b-4845-9415-233ad0608153)
2. Memilih kolom yang akan digunakan dan membuat data ke dalam satu dataframe.
3. Vektorisasi fungsi CountVectorizer dari library scikit-learn pada kolom genre. CountVectorizer digunakan untuk mengubah teks yang diberikan menjadi vektor berdasarkan frekuensi (jumlah) setiap kata yang muncul di seluruh teks. 
CountVectorizer membuat matriks di mana setiap kata unik diwakili oleh kolom matriks, dan setiap sampel teks dari dokumen adalah baris dalam matriks. Nilai setiap sel tidak lain adalah jumlah kata dalam sampel teks tertentu.

Pada proses vektorisasi ini, digunakan metode sebagai berikut. 
1. ```fit``` metode berfungsi untuk melakukan perhitungan idf pada data.
2. ```get_feature_names_out()``` berfungsi untuk melakukan mapping array dari fitur index integer ke fitur nama. Bisa dilihat pada gambar berikut:

   ![7](https://github.com/user-attachments/assets/8c87e797-a5e5-47c0-9c33-e08790e2f7c3)

3. ```fit_transform()``` berfungsi untuk mempelajari kosa kata dan Inverse Document Frequency (IDF) dengan memberikan nilai return berupa *document-term matrix*. Bisa dilihat pada gambar berikut:![6](https://github.com/user-attachments/assets/68ff2f2a-b9b0-46ab-a200-7acb35984604)

4. ```todense()``` berfungsi untuk mengubah vektor tf-idf dalam bentuk matriks. Bisa dilihat pada gambar berikut:![5](https://github.com/user-attachments/assets/3ee885cc-edf5-4988-b400-f15b50bab1d6)
   
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

## Modeling
Setelah dilakukan pra-pemrosesan pada dataset, langkah selanjutnya adalah *modeling* terhadap data. Pada tahap ini Model machine learning yang digunakan pada sistem rekomendasi ini adalah model _content-based filtering_ dengan _simlarty measure_ yang digunakan adalah _Cosine Similarity_.. 
Model _content-based filtering_ ini bekerja dengan mempelajari profil minat pengguna baru berdasarkan data dari objek yang telah dinilai pengguna. Metode ini bekerja dengan menyarankan item serupa yang pernah disukai sebelumnya atau sedang dilihat sekarang kepada pengguna berdasrakan kategori tertentu dari item yang dinilai oleh pengguna dengan menggunakan _similarity_ tertentu.

Sedangkan _cosine similarity_ adalah salah satu teknik mengukur kesamaan yang bekerja dengan mengukur kesamaan antara dua vektor dan menentukan apakah kedua vektor tersebut menunjuk ke arah yang sama dengan menghitung sudut cosinus antara dua vektor. Semakin kecil sudut cosinus, semakin besar nilai _cosine similarity_.
cara kerja dari fungsi *cosine similiraty* yaitu dengan melakukan perhitungan yang sering digunakan untuk menghitung kemiripan diantara item-item. Secara umum, fungsi similarity adalah fungsi yang menerima dua buah obyek berupa bilangan riil (0 dan 1) dan mengembalikan nilai kemiripan (similarity) antara kedua obyek tersebut berupa bilangan riil. Cosine similarity merupakan salah satu metode pengukuran kemiripan yang populer. Metode ini digunakan untuk menghitung nilai kosinus sudut antara dua vektor dan biasanya digunakan untuk mengukur kemiripan antara dua teks/dokumen. Fungsi cosine similarity antara item A dan item B ditunjukkan sebagai berikut.

![Rumus Fungsi cosin similarity](https://github.com/user-attachments/assets/23c8226c-20d2-4af5-a10a-3050824c9d89)



Keterangan:
```
𝑠𝑖𝑚(𝐴, 𝐵) = nilai similaritas dari item A dan item B
𝑛(𝐴) = banyaknya fitur konten item A 
𝑛(𝐵) = banyaknya fitur konten item B 
𝑛(𝐴 ∩ 𝐵)  = banyaknya fitur konten yang terdapat pada item A dan juga terdapat pada item B
```
Jika kedua objek memiliki nilai similaritas 1, maka kedua objek dikatakan identik dan sebaliknya. Semakin besar hasil dari fungsi similarity, maka kedua objek yang dievaluasi dianggap semakin mirip dan sebaliknya. 

* Berikut hasil dari melatih model dengan menggunakan *consine similarity* yg dapat dilihat pada gambar dibawah,![4](https://github.com/user-attachments/assets/4172269b-1497-4c56-98b8-b5a804394a5d)

* Pada tahapan ini menampilkan matriks kesamaan setiap judul dengan menampilkan judul film dalam 10 sampel kolom (axis = 1) dan 10 sampel baris (axis=0).
![3](https://github.com/user-attachments/assets/95994d98-9fd8-4896-b664-49b902eadb6c)

* Dalam pemanggilan rekomendasi judul film menggunakan function yang dibuat dengan code seperti yg terlihat pada gambar berikut
![2](https://github.com/user-attachments/assets/7e5fd96c-2b69-48f9-8e0f-37232402ce29)



Tahapan yang dilakukan pada fungsi tersebut ialah sebagai berikut.
1. Mengambil indeks dari judul film yang telah didefinisikan sebelumnnya
2. Mengambil skor kemiripan dengan semua film
3. Mengurutkan film berdasarkan skor kemiripan
4. Mengambil 10 judul berdasarkan kemiripan dari 1-11 karena urutan 0 memberikan indeks yang sama dengan judul film yang diinput
5. Mengambil judul film dari skor kemiripan
6. Mengembalikan 10 rekomendasi judul film dari kemiripan skor yang telah diurutkan dan menampilkan genre dari 10 rekomendasi film tersebut

 Berikut ini_top_10 _recommemdation_ berdasarkan genre dari judul film "*Jeffrey (1995)*"

![1](https://github.com/user-attachments/assets/407777a3-d10c-4a9d-97cf-a58cad533a3c)

judul |	genre
---|---
Big Bully (1996)	| Comedy, Drama
Antonia's Line (Antonia) (1995)	| Comedy, Drama
In the Bleak Midwinter (1995)	| Comedy, Drama
Nobody Loves Me (Keiner liebt mich) (1994)	| Comedy, Drama
Blue in the Face (1995)	| Comedy, Drama
Jeffrey (1995)	| Comedy, Drama
Love & Human Remains (1993)	| Comedy, Drama
Smoke (1995)	| Comedy, Drama
Unstrung Heroes (1995)	| Comedy, Drama
Boys on the Side (1995)	| Comedy, Drama

Dengan hasil yang diberikan pada gambar di atas berdasarkan judul film "Jeffrey (1995)" dengan genre Comedy, Drama maka didapatkan 10 rekomendasi judul film dengan genre yang serupa ataupun mirip.

## Evaluation
Pada proyek ini, Metric yang digunakan pada sistem rekomendasi judul film berdasarkan genre adalah accuracy precision. Precision adalah metrik yang membandingkan rasio prediksi benar atau positif dengan keseluruhan hasil yang diprediksi positif dengan rumus

$$\ Precission=TP/(TP+FP)$$
~~~
keterangan:
TP = True Positif (prediksi positif dan hal tersebut benar)
FP = False Positif (prediksi positif dan hal tersebut salah)
~~~
Alasan accuracy Precision dipilih adalah karena metrik ini dapat membandingkan rasio prediksi benar atau positif dengan keseluruhan hasil yang diprediksi positif. Dalam hal ini adalah rasio item yang direkomendasikan memiliki genre yang mirip atau serupa dibandingkan dengan genre dari judul film yang diinput.

Code yang digunakan untuk melihat jumlah genre yang mirip atau serupa adalah sebagai berikut.
~~~
# menghitung banyaknya data genre pada hasil rekomendasi yg dilakukan 
value = pd.DataFrame(recomendation['genre'].value_counts().reset_index().values, columns = ['genre', 'count'])
value.head()
~~~
Output:
~~~

        genre   	                        count
0	    Comedy|Drama	                    10

~~~
Dari output tersebut dihitung accuracy precision nya adalah
```
TP = 10 #jumlah prediksi benar untuk genre yang mirip atau serupa
FP = 0 #jumlah prediksi salah untuk genre yang mirip atau serupa

Precision = TP/(TP+FP)
print("{0:.0%}".format(Precision))
```
Dipilih nya nilai True Positif 10 karena merupakan nilai atau jumlah yg diduga memiliki kemiripan/identik dengan genre yg dipilih yaitu 10. hasil rekomendasi yg dihasilkan model menunjukan kemiripan dengan genre film yg dinput yaitu Comedy|Drama
sedangkan utk nilai False Positif tidak teridentifikasi pada hasil output dari genre yg diinput maka nilai nya 0 
Output:
```
100%
```
Kesimpulan dari output yang dihasilkan bahwa prediksi rekomendasi yang diberikan 100% presisi sesuai genre yang mirip atau serupa dengan genre dari judul yang diinput.

Dari hasil proses yang telah dilakukan, 2 problem statement terselesaikan dengan adanya proses data preparation diantaranya:
1. Menghitung jumlah nilai null/data kosong pada setiap kolom dengan menggunkan fungsi .isnull().sum().
2. Memeriksa dan menghapus data duplikat menggunkan fungsi .duplicate().sum().
3. Memuat dataset ke variabel baru dan mengurutkan ulang data (tranformasi data).
4. Memilih kolom yang akan digunakan dan membuat data ke dalam satu dataframe.
5. Vektorisasi fungsi CountVectorizer dari library scikit-learn pada kolom genre.

Serta mencapai goals memudahkan dalam memberi rekomendasi film berdasarkan genre dengan dibuktikannya ke akuratan 100% dalam prediksi film yang sesuai genre.
## Referensi
[1](https://www.mckinsey.com/)  McKinsey & Company. (2013): The Next Frontier for Innovation, Competition, and Productivity.

[2](https://dblp.org/rec/journals/tmis/Gomez-UribeH16.html) Gomez-Uribe, C. A., & Hunt, N. (2015): The Netflix Recommender System: Algorithms, Business Value, and Innovation.

[3](https://link.springer.com/) Ricci, F., Rokach, L., & Shapira, B. (2015): Recommender Systems Handbook. Springer.

[4](https://www.sciencedirect.com/) Sharma, S., & Garg, R. (2020): Personalized Recommender Systems: Integration of Deep Learning and Big Data.
