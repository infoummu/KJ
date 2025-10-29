---
title: Tugas Pengganti - Manajemen Hak Akses dalam Sistem Linux P-6
category: Materi
author: Ikhwan Elyas
published: true
description: Manajemen hak akses dan keamanan file sangat penting dalam Keamanan Sistem dan Jaringan Komputer karena memastikan setiap data hanya dapat diakses oleh pengguna yang berwenang. Pengaturan izin yang benar melindungi informasi sensitif dari pencurian, modifikasi, atau penghapusan yang tidak sah. Dalam sistem multi-user, seperti server jaringan, kesalahan izin dapat menjadi celah serangan yang dimanfaatkan hacker untuk mengambil alih sistem. Dengan pengelolaan hak akses yang tepat, integritas, kerahasiaan, dan ketersediaan data dapat tetap terjaga.
---

### 📌 Pertemuan Pengganti
 
**Mata Kuliah:** Keamanan Sistem dan Jaringan Komputer  
**Topik:** Permission & Ownership Security  
**Tujuan Tugas dan Topik:**  
Mahasiswa memahami dan menerapkan konsep hak akses, kepemilikan, dan keamanan file dalam sistem Linux.

---

### ⚠️ Instruksi Tugas

1️⃣ Silakan login ke server menggunakan akun masing-masing:

```bash
# sesuaikan dengan USERNAME dan IP Addressnya
ssh mhs-22008@192.168.77.10

```

2️⃣ Baca dan Lakukan Latihan dari **Bagian 1** sampai **Bagian 4**,

3️⃣ Catat dan buat screenshot setiap hasil dan sertakan ke dalam Laporannya,

4️⃣ Buat Laporan dalam format PDF, instruksi ISI file PDF ada di bagian bawah (Panduan Laporan)


---

### ✅ Bagian 1 — Menambahkan Hak Akses sudo untuk User masing2

**Langkah 1 — Login sebagai user yang punya akses sudo (misal: infra)**

```bash
#ssh infra@IP (sesuaikan)
ssh infra@192.168.77.10
```
ATAU, langsung menggunakan akun masing2,

```bash
ssh mhs-22000@192.168.77.10

#setelah itu 

su - infra
```

**Langkah 2— Tambahkan user ke grup sudo** 

Ganti <npm> dengan NPM anda, contoh: `mhs-22000`

```bash
# sudo usermod -aG sudo mhs-<npm>
sudo usermod -aG sudo mhs-22000
```

**Langkah 3 — Verifikasi**
```bash
#contoh 
# groups mhs-22000
groups mhs-<npm>
```
Pastikan output ada kata sudo.

**Langkah 4 — Uji coba sudo**

Login lagi sebagai user masing2:

```bash
# su - mhs-<npm>
su - mhs-22000

# Setelah itu : 
sudo ls /root
```

Jika muncul prompt password dan berhasil akses → ✅ sudah berhasil.


### ✅ Bagian 2 — Pembuatan Struktur Direktori
Buat struktur folder berikut di dalam **HOME** masing-masing:

```
/home/mhs-22000/
         └── proyek_keamanan/
            ├── data_rahasia/
            ├── data_publik/
            └── log_aktivitas.txt
```

Perintah bantu (opsional):
```bash
mkdir -p ~/proyek_keamanan/data_rahasia
mkdir -p ~/proyek_keamanan/data_publik
touch ~/proyek_keamanan/log_aktivitas.txt
```

---

### ✅ Bagian 3 — Pengaturan Permission & Ownership

| Lokasi | Permission | Keterangan |
|--------|------------|------------|
| `data_rahasia/` | Hanya owner yang boleh read & write | **Tidak boleh diakses user lain** |
| `data_publik/` | Owner + Group bisa read & write | Others hanya read |
| `log_aktivitas.txt` | Hanya owner read & write | File sensitif catatan aktivitas |

Gunakan perintah:  
- `chmod`  
- `chown`  
- `ls -l` untuk mengecek hasil

Contoh:
```bash
chmod 700 ~/proyek_keamanan/data_rahasia
chmod 764 ~/proyek_keamanan/data_publik
chmod 600 ~/proyek_keamanan/log_aktivitas.txt
```

---

### ✅ Bagian 4 — Uji Coba Keamanan
Lakukan uji akses dengan cara berganti user lain dan cek:

- Apakah direktori **data_rahasia** benar-benar tidak bisa diakses?
- Apakah **data_publik** bisa dibaca user lain?
- Apakah **log_aktivitas.txt** tidak dapat dibaca user lain?

Gunakan:
```bash
sudo su - <user_lain>
```

Catat hasilnya!

---

### 📄 Panduan Laporan yang Dikumpulkan (PDF)

Isi laporan minimal meliputi:

1️⃣ Tema, Nama, NPM, dan Kelas 
2️⃣ Tujuan Latihan dan praktik  
3️⃣ Hasil screenshot atau output perintah:
   - `ls -l` seluruh struktur direktori
   - Bukti uji coba akses
4️⃣ Analisis singkat:
   - Mengapa hak akses **penting** dalam keamanan?
   - Contoh ancaman jika izin salah diterapkan
5️⃣ Kesimpulan

---

## ⏱️ Deadline
- Dikumpulkan Maksimal **satu Hari Sebelum Masuk** pada **pertemuan berikutnya**,
- Isi `Absen` dan `Upload` File Tugas `PDF` lewat link berikut: **[[Absen dan Upload PDF](https://ksj.tifor.site/){:target="_blank"}]**.


---
by: IkhwanElyas@fedora.linux