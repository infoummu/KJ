---
title: Teknik Transposisi Dan One Time Pad
category: Materi
author: Merlan Kolong (21003)
published: true
---
**KATA PENGANTAR**

Puji syukur kami panjatkan kehadirat Tuhan Yang Maha Esa,  karena berkat rahmatnya kami dapat menyelesaikan tugas makalah ini, tugas ini diajukan guna memenuhi tugas mata kuliah keamanan jaringan.
Makalah ini masih jauh dari sempurna, oleh karena itu kami mengharapkan kritik dan saran yang bersifat membangun demi kesempurnaan makalah ini.
Semoga makalah ini memberi informasi dan wawasan yang lebih luas bagi masyarakat khususnya mahasiswa dan bermanfaat untuk pengembangan ilmu pengetahuan bagi kita semua. 

**PENDAHULUAN**

Perkembangan teknologi yang begitu pesat memungkinkan manusia dapat berkomunikasi dan saling bertukar informasi/data pada jarak jauh. Perkembangan dunia komputer dan pendukung perangkat lainnya yang serba digital, telah membuat data-data digital semakin banyak digunakan. Terdapat sejumlah faktor yang membuat data digital (seperti audio, video, citra dan teks) semakin banyak digunakan ( Amin, 2014) antara lain: 
1. Mudah diduplikasi dan hasilnya sama dengan aslinya. 
2. Mudah untuk penduplikasian dan penyimpanan. 
3. Mudah disimpan untuk kemudian diolah atau diproses lebih lanjut.
4. Serta mudah didistribusikan, baik dengan media disk maupun melalui jaringan internet
   
Kerahasiaan pesan atau data yang dimiliki oleh seseorang merupakan hal penting dalam pengiriman pesan agar hanya orang tertentu saja yang dapat mengakses pesan tersebut. Untuk menjaga kerahasiaan pesan diperlukan pengamanan data atau dikenal sebagai kriptografi. Kriptografi adalah sebuah cara untuk mengamankan informasi. Informasi yang harus dijaga kerahasiaannya haruslah diubah menjadi sebuah informasi yang tidak bisa dibaca oleh orang selain yang berhak membacanya. Kriptografi, secara umum adalah ilmu dan seni untuk menjaga kerahasiaan informasi. (Nurhayati, 2013). Kriptografi disebut sebagai ilmu karena didalamnya terdapat metode (rumusan) yang digunakan, dan dikatakan sebagai seni karena karena dalam membuat suatu teknik kriptografi itu sendiri merupakan ciri tersendiri dari si pembuat dan memerlukan teknik khusus dalam mendisainnya. Orang-orang yang mendalami dan mengimplementasikan kriptografi disebut cryptographer, sedangkan cryptanalysis adalah suatu ilmu dan seni memecahkan ciphertext menjadi plaintext tanpa melalui cara yang seharusnya dan orang yang melakukannya disebut cryptanalyst.

 
**PEMBAHASAN**

**A. Teknik Kriptografi Transposisi dan One Time Pad**

Kriptografi adalah ilmu mengenai teknik enkripsi dimana “naskah asli” (plaintext) diacak menggunakan suatu kunci enkripsi menjadi “naskah acak yang sulit dibaca” (ciphertext) oleh seseorang yang tidak memiliki kunci dekripsi. Dekripsi menggunakan kunci dekripsi bisa mendapatkan kembali data asli. Probabilitas mendapat kembali naskah asli oleh seseorang yang tidak mempunyai kunci dekripsi dalam waktu yang tidak terlalu lama adalah sangat kecil. 
  
Teknik enkripsi yang digunakan dalam kriptografi klasik adalah enkripsi simetris dimana kunci dekripsi sama dengan kunci enkripsi. Untuk public key cryptography, diperlukan teknik enkripsi asimetris dimana kunci dekripsi tidak sama dengan kunci enkripsi. Enkripsi, dekripsi dan pembuatan kunci untuk teknik enkripsi asimetris memerlukan komputasi yang lebih intensif dibandingkan enkripsi simetris, karena enkripsi asimetris menggunakan bilangan – bilangan yang sangat besar. (Kromodimoeljo, 2010). 
 
**B. Teknik Transposisi**

Metode penyandian transposisi adalah metode penyandian dengan cara mengubah letak dari teks pesan yang akan disandikan. Untuk membaca pesan aslinya kembali, cukup dengan mengembalikan letak dari pesan tersebut berdasarkan kunci dan algoritma pergeseran huruf yang telah disepakati.
 
 Sebelumnya sudah dijelaskan bahwa metode kuno/ klasik terdiri dari 2 teknik yaitu:
 1. Teknik Subtitusi, contoh: kode kaisar (geser, monoalphabet, polyalphabet, playfair, dan lainnya)
    
 2. Teknik Permutasi, contoh: kode transposisi. Teknik ini menggunakan permutasi karakter, yang mana dengan menggunakan teknik ini pesan  asli tidak dapat dibaca kecuali oleh orang yang memiliki kunci untuk mengembalikan pesan tersebut ke bentuk semula.
    
 Sebagai contoh, ada 6 kunci untuk melakukan permutasi kode:
 
 ![image](https://github.com/user-attachments/assets/adc8dcb1-ff73-4166-aff5-faf829f2231b)

*Gambar 6.1 Kunci Permutasian Kode*

Dan 6 kunci untuk inversi dari permutasi tersebut: 

![image](https://github.com/user-attachments/assets/1f27b4ee-21ec-4de5-8239-c764b7797c54)

*Gambar 6.2 Kunci Inversi dari Permutasian Kode*

Terlebih dahulu plaintext dibagi menjadi beberapa blok dan tiap blok nya terdiri dari 6 karakter, jika terjadi kekurang pada setiap blok maka disisipkan karakter yang disepakati sebelumnya. 31 Perhatikan contoh dibawah ini: 

Plaintext : **PERHATIKAN RAKYAT KECIL** Cara memutasi plaintext, yaitu :

 ![image](https://github.com/user-attachments/assets/411acc7d-5147-4707-9cf3-5066c30362c4)

Gambar 6.3 *Hasil Teknik Transposisi permutasian kode*

Ciphertext : **RAPTHEARIANKAKKETYLXCXXI**

Sedangkan kunci inverse berfungsi untuk mengubah ciphertext menjadi plaintext. 

Perhatikan contoh dibawah ini: 

![image](https://github.com/user-attachments/assets/ca4ee4c1-ad54-4c8d-8168-dc67ac8a59e6)

  Gambar 6.4 *Hasil Plaintext Transposisi Permutasian*
  
 Selain teknik mutasi-inversi ada beberapa teknik permutasi lainnya yaitu dengan menggunakan permutasi zigzag, segitiga, spiral, dan   diagonal. 
 
1.	Zig-zag Dengan memasukan plaintext seperti pola zig-zag.

Plaintext: **PERHATIKAN RAKYAT KECIL**

![image](https://github.com/user-attachments/assets/247d7f0f-9680-4597-a7bc-41e6f6214ba9)
 
  Gambar 6.5 *Contoh Teknik Permutasian Pola Zigzag*
    
 Ciphertext : **HNTXRAARAKLETKAYEIPIKC**
 
2.	Segitiga Dengan memasukan plaintext sepeti pola segitiga.
   
Plaintext: **PERHATIKAN RAKYAT KECIL**

![image](https://github.com/user-attachments/assets/ba84456d-b165-4642-931e-89590ee2b60f)
 
Gambar 6.6. *Contoh Teknik Permutasian Pola Segitiga*

Ciphertext : **KNEARCETAIPRIKLHKYXAAXTXX**

3.	Spiral Dengan memasukan plaintext disusun seperti pola spiral.
   
Plaintext: **PERHATIKAN RAKYAT KECIL**

![image](https://github.com/user-attachments/assets/b6eda3d3-091b-4d7a-93a9-b562601a7e21)

 Gambar 6.7 *Contoh Teknik Permutasian Pola Sprial 1*

 Ciphertextnya : **PTAYKEKXXAREXXRHCILNATIKA**
 
4.	Diagonal Dengan memasukan plaintext disusun seperti pola dibawah ini.
   
Plaintext: **PERHARTIKAN RAKYAT KECIL**

![image](https://github.com/user-attachments/assets/28438156-09ee-4454-84d4-871a264ca646)
 
Gambar 6.8 *Contoh Teknik Permutasian Pola Spiral 2*

Ciphertextnya : **PTRTLEIAKXRKKEXHAYCXANAIX**

**C. One Time Pad** 

Pada umumnya algoritma kriptografi tidaklah sempurna, tetapi untuk mendapatkan algoritma yang lebih baik dan mempunyai sedikit kemunngkinan untuk dipecahkan adalah one time pad (OTP). Salah satu konsep OTP adalah dengan menggunakan enkripsi super. Contoh pada metode ini yaitu : 

Plaintext : **PERHATIKAN RAKYAT KECIL**

1.	Menggunakan teknik subtitusi dengan algoritma kode geser sebanyak 7 
 
 ![image](https://github.com/user-attachments/assets/6e6c6244-1dff-4c80-b082-dc1a64a249e3)

Gambar 6.9 *Teknik One Time Pad geser 7*

Ciphertext dari hasil teknik subtitusi di ubah menjadi ciphertext dengan teknik transposisi.

2.	Menggunakan teknik transposisi dengan teknik diagonal dengan kunci 5 x 5. 

![image](https://github.com/user-attachments/assets/a0e22766-be65-4350-a484-0aa03181b704)
 
Gambar 6.10 *Teknik One Time Pad diagonal 5x5*

 Ciphertext : **VZXZRKOGQXXQQKXNGEIXGTGOX**.

Teknik dari enkripsi super sangat penting dan banyak dari algoritma enkripsi modern yang menggunakan teknik ini sebagai dasar pembuatan suatu algoritma modern.


**Referensi**

*Saragih,N.,Enjelita. IMPLEMENTASI ALGORITMA ONE TIME PAD PADA PESAN*

*Jurnal ilmiah MATRIX Vol.20 No.1, April 2018*.

*BUKU AJAR KEAMANAN INFORMASI DAN JARINGAN KOMPUTER, PANDU PRATAMA PUTRA, M.KOM, MTA DAFWEN TORESA, M.KOM, MTA*.
