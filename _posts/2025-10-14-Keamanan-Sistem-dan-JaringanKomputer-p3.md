---
title: Implementasi Dasar Keamanan Jaringan (Linux) P-4
category: Materi
author: Ikhwan Elyas
published: true
---


### Mata Kuliah: Keamanan Sistem dan Jaringan Komputer
Implemantasi dasar Keamanan Sistem dan Jaringan Komputer dalam ruang lingkup Sistem Operasi Linux.

#### 🎯 Tujuan Pembelajaran
Mahasiswa memahami dan mampu menggunakan perintah-perintah dasar Linux untuk administrasi sistem dan jaringan, sebagai langkah awal memahami keamanan sistem operasi.

---

### 🧠 Tugasnya, Bagian Tahapan 

1. Masuk ke vps (Virtual Private Server) yang **USER** dan **IP** akan di share lewat **WA** (**untuk keamanan**)

   ```bash
   # contoh : 
   ssh  infra@192.168.77.10
   ```

2. Buat USER BARU dengan **nama user mhs-NPM anda** (lima digit terakhir) dan SET Passwordnya (diingat dan dicatat)

   ```bash
   # contoh nama user = mhs-22002
   # sudo adduser (NPM)
   sudo adduser mhs-22002

   ```

3. Jika sudah berhasil, lanjut exit (keluar) dari user yang dipakai bersama dan masuk lagi dengan user yang baru anda buat 
```bash
# contoh : 
# ssh  npm@192.168.77.10
ssh 22001@@192.168.77.10
```

4. Selanjutnya, gunakan **user** dan **pass** tersebut untuk melakukan latihan dan kebutuhan belajar MK ini seterusnya

### 🧩 Bagian 1: Akses ke Server VPS Bersama

#### 🔐 Informasi Akses
- **Server:** mhs-npm@192.168.77.10  
- **Port:** 22 (standar)  
- **Metode Akses:** SSH
- **Password Akses:**   

#### 🖥️ Perintah Login
```bash
# contoh : 
ssh  npm-mhs@192.168.77.10
```

Jika diminta konfirmasi fingerprint, ketik `yes`, lalu masukkan password yang diberikan oleh dosen/asisten.

---

#### ⚙️ Bagian 2: Pengenalan Lingkungan Linux

Setelah berhasil login, lakukan langkah-langkah berikut:
1. Lakukan Latihan dengan urutan perintah dibawah
2. Semua Perintah yang menghasilkan output, simpan hasil outputnya ke file `praktiku1_npm.txt`

#### 1️⃣ Mengecek siapa kamu dan di mana kamu berada
```bash
# contoh
whoami
whoami >> praktiku1_22000.txt
pwd
```

#### 2️⃣ Melihat isi direktori dan berpindah direktori
```bash
ls
ls -l
cd /home
cd ~
```

#### 3️⃣ Membuat, menyalin, memindahkan, dan menghapus file/direktori
```bash
mkdir latihan_linux
cd latihan_linux
touch file1.txt
cp file1.txt file2.txt
mv file2.txt /tmp/
rm file1.txt
rmdir latihan_linux
```

#### 4️⃣ Melihat isi file dan isi direktori dengan lebih detail
```bash
cat /etc/os-release
less /etc/passwd
head /var/log/syslog
tail -n 10 /var/log/syslog
```

#### 5️⃣ Mengecek status sistem
```bash
uname -a
uptime
df -h
free -m
top
```

#### 6️⃣ Manajemen user dasar (lihat saja, jangan ubah!)
```bash
who
w
id
cat /etc/group
```

#### 7️⃣ Mengecek koneksi dan jaringan
```bash
ip a
ping -c 3 8.8.8.8
netstat -tuln
```

---


📘 **Catatan:**  
Pastikan Anda **tidak mencoba menjalankan perintah yang mengubah konfigurasi sistem**, kecuali diinstruksikan. Semua aktivitas login dan perintah akan direkam untuk evaluasi.

---

💡 *“Penguasaan keamanan dimulai dari pemahaman sistem.”*

---
by: IkhwanElyas@linux.fedora