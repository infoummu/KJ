---
title: Teknik Transposisi Dan One Time Pad
category: Materi
author: Merlan Kolong (21003)
published: true
---
**KATA PENGANTAR**

syukur kami panjatkan kehadirat tuhan Yang Maha Esa ,  Esa yang telah memberikan Kesehatan serta karunianya kepada kami sehingga kami berhasil menyelesaikan makalah ini yang berjudul “KEMANAN DATABASE”. Dalam penyusunan makalah ini disusun berdasarkan syarat dan ketentuan yang diberikan oleh dosen, untuk pengambilan bahan tugas sebagai pelengkap dari isi makalah yang akan disusun. Bahan-bahan tersebut diambil dari referensi, dari buku. Dalam pembuatan makalah ini masih banyak kekurangan, oleh karena itu penulis mengharapkan saran dan kritik yang bersifat membangun dari semua pihak yang berkepentingan dengan makalah ini. Akhir saya ucapkan trimah kasih.  

**PENDAHULUAN**

Keamanan database adalah proses, alat dan control yang mengamankan dan melindungi database dari ancaman yang tidak sengaja dan disengaja. Tujuan keamanan database adalah untuk mengamankan data sensitive dan menjaga kerahasiaan, ketersediaan dan integritas database. Perkembangan teknologi informasi saat ini membawa dampak yang sangat besar yaitu masalah keamanan dan kerahasiaan sebuah data yang merupakan hal yang sangat penting agar terhindarnya suatu proteksi terhadap pengrusakan data dan pemakaian data oleh pihak-pihak yang tidak bertanggung jawab yang memanfaatkan celah-celah keamanan agar dapat melihat, mengambil serta memanipulasi data. Oleh karena itu, diperlukan sebuah sistem atau aplikasi yang aman sehingga tidak mudah dibaca oleh pihak yang tidak punya kewenangan. Salah satu solusi yang dapat digunakan untuk menjamin kerahasiaan dan keamanan suatu informasi adalah kriptografi. Dengan menggunakan kriptografi, maka suatu data dapat diamankan melalui proses dekripsi dan enkripsi.

**PEMBAHASAN**

**A. TIU**
 1) Memahami teknik-teknik pengamanan database yang handal
 2) Mengenali perlindungan terhadap data yang sensitif 
3) Merangkum masalah-masalah keamanan dalam penggunaan database
 4) Memahami konsep database multilevel
 5) Memahami konsep keamanan bertingkat dalam database 

**B. Konsep Dasar Keamanan Database**

Database atau basis data merupakan salah satu perangkat yang sangat vital bagi sebuah organisasi. Karena database mengandung informasi yang sangat sensitif yang harus dilindungi dari kerentanan dan eksploitasi keamanan. Seluruh perangkat organisasi harus bekerja terus menerus untuk mengidentifikasi dan memulihkan kerentanan tersebut dengan menggunakan berbagai alat yang tersedia. Selain itu, penting untuk melakukan analisis dan audit untuk memastikan bahwa postur keamanan basis data tetap baik, dan juga menunjukkan kepatuan terhadap dokumen kebijakan yang menuntuk tingkat keamanan tinggi.

**C. Keamanan database**

merupkan suatu cara untuk melindungi database dari ancaman, baik dalam bentuk yang disengaja maupun bukan. Artian ancaman disini berarti segala situasi yang sifatnya mempengaruhi sistem atau bahkan merugikan. Pada sebuah sistem database dikenal istilah administrator database. Administrator database memegang peranan penting karena mempunyai hak untuk mengontrol dan mengatur database. 
Hampir semua organisasi menggunakan database dalam beberapa bentuk untuk melacak informasi seperti catatan pelanggan dan transaksi, informasi keuangan, dan catatan lainnya (Howard, 2013). Database yang mengandung banyak data sensitive ini dapat dijual atau dicuri yang menyebabkan organisasi tersebut kehilangan bisnis atau reputasi. Terutama jika organisasi tersebut ditemukan melanggar peraturan atau standar industry yang menuntuk tingkat keamanan data yang tinggi, contoh bank. 

**10 ancaman teratas terkait database menurut Aplication Security, Inc., adalah sebagai berikut:** 

1. Password yang lemah 
2. SQL injection 
3. Hak user dan grup yang berlebihan 
4. Fitur-fitur DBMS yang tidak perlu diaktifkan 
5. Manajemen konfigurasi yang rusak
6. Buffer overflow 
7. Hak istimewa untuk beberapa user 
8. Keagalan layanan 
9. Un-patched RDBMS 
10. Data tidak terenkripsi
    
 **D. Kategori Keamanan Database**

 Diambil dari Panduan Penangan Insiden Keamanan Database oleh Badan Pengkajian dan Penerapan Teknologi Kementerian Komunikasi dan Informatika Republik Indonesia Tahun 2014, berikut garis besar kategori keamanan database:
 
  a. Keamanan Server

Perlindungan Server adalah suatu proses pembatasan akses yang sebenarnya pada database dalam server itu sendiri. Menurut Blake Wiedman ini adalah suatu sisi keamanan yang sangat penting dan harus direncanakan secara hati-hati. Ide dasarnya adalah kita tidak dapat mengakses apa yang kita tidak dapat lihat, atau apakah kita ingin database server kita dapat dilihat oleh orang lain. Database bukanlah suatu web server, dimana koneksi yang tidak dikenali tidak diijinkan.

  b. Trusted Ip Access

Setiap server harus dapat mengkonfigurasikan alamat ip yang diperbolehkan mengakses dirinya. Sebagaimana tidak mengijinkan orang lain memasuki rumah seseorang tanpa ijin maka tidak dapat pula mengijinkan semua orang dapat mengakses server dari sebuah organisasi. Jika server melayani suatu web server maka hanya alamat web server itu saja yang dapat mengakses server database tersebut. Jika server database melayani jaringan internal maka hanya alamat jaringanlah yang boleh menghubungi server. Sangat perlu diperhatikan bahwa jangan pernah menggabungkan server database web dengan server database informasi internal perusahaan anda, ini adalah suatu mental yang buruk untuk seorang admin. Trusted Ip Access merupakan server database terbatas yang hanya akan memberi respon pada Ip yang dikenali saja

  c. Database Connection

Saat ini semakin banyaknya aplikasi dinamis menjadi sangat menggoda untuk melakukan akses yang cepat bahkan update yang langsung tanpa authentifikasi. Jika kita ingin mengijinkan pemakai dapat mengubah database melalui web page, pastikan memvalidasi semua masukan untuk memastikan bahwa inputan benar, terjamin dan aman.Sebagai contoh, pastikan menghilangkan semua code SQL agar tidak dapat dimasukan oleh user. Jika seorang admin yangmembutuhkan koneksi ODBC, pastikan koneksi yang digunakan unik

  d. Table Access Control
 
Kontrol akses table ini adalah salah satu bentuk keamanan database yang sering diabaikan,karena cukup sulit penerapannya. Penggunaan control akses table yang benar dibutuhkan kolaborasi antara system administrator dengan pengembang database. Hal inilah yang sulit dilakukan. Pemberian ijin user untuk mengakses informasi dapat membuat informasi terbuka kepada public. Jika seorang user mengakses informasi apakah akan dilihat menggunakan session yang samaa tau jika tabel digunakan sebagai referensi sistem mengapa ia diberikan ijin selain hak membaca saja.

 E. 5 Tahap Keamanan pada Database
 
Terdapat 5 langkah utama untuk memastikan keamanan database menurut Application Security, Inc.

1) Pisahkan database sensitif. Pertahankan inventaris yang akurat dari semua database yang digunakan di seluruh organisasi/perusahaan dan identifikasi semua data sensitif yang berada di database tersebut.
   
2) Eliminasi kerentanan. Terus menerus melakukan identifikasi dan memulihkan kerentanan yang mengekpos database.
   
3) Enforce least privileges. Identifikasi hak pengguna dan menegakkan kontrol akses dan hak istimewa penggunauntuk membatasi akses hanya pada data minimum yang diperlukan bagi karyawan untuk melakukan pekerjaan.
   
4) Pantau penyimpangan/anomali. Terapkan kebijakan yang sesuai dan pantau kerentanan yang tidak dapat diperbaiki untuk setiap dan semua kegiatan yang menyimpang dari kegiatan yang diperbolehkan.
    
5) Tanggapi perilaku yang mencurigakan. Waspada dan tanggapi perilaku abnormal atau mencurigarakan secara real time untuk meminimalkan resiko serangan.
     
**E. Best Practice pada Keamanan Database**

Langkah pertama untuk memastikan keamanan database adalah dengan mengembangkan rencana keamanan database yang mempertimbangakn penggunaan standar keamanan yang harus dipatuhi oleh organisasi. Sebagai bagian dari pengembangan rencana ini, organisasi harus melakukan inventarisasi semua database dalam lingkungan jaringan organisasi. Hal ini dapat dilakukan secara lebih efisien melalui penggunaan teknologi manajemen kerentanan yang dapat secara otomatis menemukan semua database dan menjalankan pemindaian untuk mengidentifikasi yang mengandung data sensitif, seperti data keuangan dan data pelanggan. Penilaian yang dilakukan oleh teknologi tersebut akan dapat menilai kerentanan database dan kesalah konfigurasi, mengidentifikasi masalah sepertifi password yang lemah, kontrol akses yang buruk, dan mencari tahu kerentanan mana yang dapat dieksploitasi sehingga dapat memprioritaskan perbaikan terhadap kesalahan/kerentanan tersebut. 

Teknologi seperti Database Activity Monitoring (DAM) akan membantu dalam proses mengurangi kerentanan dengan memberikan visibilitas secara real time ke semua aktivitas database. Data akan dikumpulkan dan dianalisis untuk mencari kegiatan yang melanggar kebijakan keamanan atau yang mengindikasikan anomali terjadi. 

Langkah penting lain yaitu memastikan penggunaan password yang baik (strong password) yang digunakan untuk mengenkripsi data. Sering kali password bawaan (default password) tidak diubah oleh pengguna sehingga bisa menjadi salah satu penyebab anomali terjadi. Untuk tahapan lebih lanjut dalam melindungi data/informasi, maka semua data harus disimpan dalam database dalam keadaan yang sudah terenkripsi, dengan catatan akses ke kunci enkripsi terkontrol dan dipantau dengan ketat. 

Salah satu aspek lain yang perlu dipertimbangkan dalam menjaga keamanan database adalah dengan pelatihan keamanan dan kesadaran karyawan. Hal ini dilakukan untuk memastikan bahwa semua karyawan mengetahui kebijakan keamanan organisasi dan praktik terbaik yang disyaratkan.  Pelatihan yang berkelanjutan dianggap sebagai praktik terbaik dalam mencegah data sensitif terekspos keluar.

**REFERENSI**

*Simanjuntak, M., Pasaribu, T., Rahmadilla, S. Implementasi Algoritma Merkle Hellman untuk Keamanan Database, Volume 4 No. 1, Januari - Juni 2019.
Buku Sistem Keamanan, Nurul Hayaty, M.Cs.*
