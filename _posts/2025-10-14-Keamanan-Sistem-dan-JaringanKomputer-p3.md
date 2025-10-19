---
title: Pertemuan 3 - Praktik Perintah Dasar Linux
category: Materi
author: Ikhwan Elyas
published: true
---

### 🧠 Pertemuan 3: Praktik Dasar Linux
#### Mata Kuliah: Keamanan Sistem dan Jaringan Komputer

#### 🎯 Tujuan Pembelajaran
Mahasiswa memahami dan mampu menggunakan perintah-perintah dasar Linux untuk administrasi sistem dan jaringan, sebagai langkah awal memahami keamanan sistem operasi.

---


## 🧠 Bagian Tahapan Praktikum

1. Buat direktori bernama `praktikum_npm`
2. Setelah itu masuk dengan perinah `cd praktikum_npm`
3. Di dalamnya buat file `hasil_praktiku3_npm.txt` dengan perintah `touch hasil_praktiku3_npm.txt` 
4. Isi file `hasil_praktiku3_npm.txt` dengan perintah `nano hasil_praktiku3_npm.txt`:
   ```
   Nama: [Nama Lengkap]
   NPM : [NPM Anda]
   Waktu Login: [hasil dari perintah date]
   ```
4. Setelah itu Pastikan hasilnya dapat dilihat dengan:
   ```bash
   cat hasil_praktiku3_npm.txt
   ```

## 🧩 Bagian 1: Akses ke Server Praktikum

### 🔐 Informasi Akses
- **Server:** infra@192.168.77.10  
- **Port:** 2222  
- **Metode Akses:** SSH
- **Password Akses:**   

### 🖥️ Perintah Login
```bash
ssh -p 2222 infra@192.168.77.10
```

Jika diminta konfirmasi fingerprint, ketik `yes`, lalu masukkan password yang diberikan oleh dosen/asisten.

---

### ⚙️ Bagian 2: Pengenalan Lingkungan Linux

Setelah berhasil login, lakukan langkah-langkah berikut:
1. Lakukan Latihan dengan urutan perintah dibawah
2. Semua Perintah yang menghasilkan output, simpan hasil outputnya ke file `hasil_praktiku3_npm.txt`

### 1️⃣ Mengecek siapa kamu dan di mana kamu berada
```bash
whoami
pwd
```

### 2️⃣ Melihat isi direktori dan berpindah direktori
```bash
ls
ls -l
cd /home
cd ~
```

### 3️⃣ Membuat, menyalin, memindahkan, dan menghapus file/direktori
```bash
mkdir latihan_linux
cd latihan_linux
touch file1.txt
cp file1.txt file2.txt
mv file2.txt /tmp/
rm file1.txt
rmdir latihan_linux
```

### 4️⃣ Melihat isi file dan isi direktori dengan lebih detail
```bash
cat /etc/os-release
less /etc/passwd
head /var/log/syslog
tail -n 10 /var/log/syslog
```

### 5️⃣ Mengecek status sistem
```bash
uname -a
uptime
df -h
free -m
top
```

### 6️⃣ Manajemen user dasar (lihat saja, jangan ubah!)
```bash
who
w
id
cat /etc/group
```

### 7️⃣ Mengecek koneksi dan jaringan
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
