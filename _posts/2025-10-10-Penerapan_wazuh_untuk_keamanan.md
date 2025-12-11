---
title: 🛡️ Tugas Proyek Mahasiswa - Penerapan Wazuh
category: Materi
author: Ikhwan Elyas
published: true
description: Mahasiswa mampu menginstal, mengkonfigurasi, dan menggunakan platform **Wazuh** untuk memantau aktivitas keamanan dasar pada beberapa sistem operasi yang berbeda, sekaligus mengaplikasikan konsep **SIEM (Security Information and Event Management)** dan **IDS (Intrusion Detection System)** secara praktis.
---



## Judul Proyek: **Implementasi Wazuh SIEM untuk Pemantauan Keamanan Multi-Endpoint**

---

### 👥 Detail Tugas

| Kriteria | Keterangan |
| :--- | :--- |
| **Sifat Tugas** | Kelompok (Maksimal 4 Orang) |
| **Target Implementasi** | 1 Server, Minimal **2 Client/Agent** |
| **Contoh Client** | 1 Server Linux (misalnya Ubuntu/Debian/CentOS) dan 2 Client Linux & Windows |
| **Output Laporan** | Dokumen PDF sesuai format yang ditentukan |

### 🎯 Tujuan Pembelajaran

Mahasiswa mampu menginstal, mengkonfigurasi, dan menggunakan platform **Wazuh** untuk memantau aktivitas keamanan dasar pada beberapa sistem operasi yang berbeda, sekaligus mengaplikasikan konsep **SIEM (Security Information and Event Management)** dan **IDS (Intrusion Detection System)** secara praktis.

---

### 🛠️ Langkah-Langkah Penerapan Proyek (Scope Proyek)

Setiap kelompok wajib mendokumentasikan langkah-langkah berikut dalam laporannya:

#### 1. Persiapan Lingkungan (Wazuh Manager)
* Melakukan instalasi **Wazuh Manager** (termasuk komponen Elastic Stack/OpenSearch) pada sebuah mesin virtual/server.
* Memastikan antarmuka visual (Kibana/OpenSearch Dashboards) dapat diakses.

#### 2. Instalasi dan Registrasi Agent
* Menginstal **Wazuh Agent** pada **Client 1** (misalnya Linux).
* Menginstal **Wazuh Agent** pada **Client 2** (misalnya Windows).
* Mendaftarkan kedua Agent ke Wazuh Manager dan memverifikasi statusnya **Aktif (Active)**.

#### 3. Uji Coba Fungsi Keamanan (Minimum Requirement)

**A. File Integrity Monitoring (FIM)**
* Konfigurasi Agent pada salah satu Client untuk memantau perubahan pada file/direktori penting (misalnya `/etc/hosts` atau folder *Startup* Windows).
* Lakukan perubahan (edit, hapus, atau buat) pada file/direktori yang dipantau.
* **Dokumentasikan *Alert* yang muncul di Wazuh Dashboard.**

**B. Log Analysis/Intrusion Detection (IDS)**
* Simulasikan upaya serangan *Brute-force* dengan melakukan **5-10 kali** upaya *login* gagal secara berturut-turut pada salah satu Client (melalui SSH di Linux atau Remote Desktop/Console di Windows).
* **Dokumentasikan *Alert* Wazuh (yang memiliki *Rule ID* terkait *Multiple failed logins*) yang terpicu.**

---

### 📑 Struktur Laporan Proyek (Wajib Format PDF)

Laporan harus mencakup poin-poin berikut dengan tata letak yang jelas:

#### 4.1. Halaman 1: Profil Kelompok (Cover)
* **Judul Tugas:** Implementasi Wazuh SIEM untuk Pemantauan Keamanan Multi-Endpoint
* **Mata Kuliah:** Keamanan Sistem dan Jaringan Komputer
* **Nama Dosen Pengampu:** (Sebutkan Nama Dosen Anda)
* **Disusun Oleh:**
    * Nama Anggota 1 (NIM)
    * Nama Anggota 2 (NIM)
    * Nama Anggota 3 (NIM)
    * Nama Anggota 4 (NIM)
* **Program Studi:** (Sebutkan Program Studi Anda)
* **Nama Kampus:** (Sebutkan Nama Kampus Anda)

#### 4.2. Pembahasan, Penerapan, dan Dokumentasi
Bagian inti laporan. Wajib menggunakan **Screenshot** dan penjelasan rinci di setiap langkah.

* **A. Deskripsi Arsitektur:** Topologi yang digunakan (Manager dan 2 Client).
* **B. Tahapan Instalasi Manager:** Detail langkah dan **[Screenshot]** Dashboard setelah berhasil.
* **C. Instalasi Agent (Client 1 & 2):** Detail langkah dan **[Screenshot]** status *Active* di Manager.
* **D. Dokumentasi Uji Coba FIM:** Penjelasan, simulasi perubahan, dan **[Screenshot]** *Alert* Wazuh.
* **E. Dokumentasi Uji Coba IDS/Brute-force:** Penjelasan, simulasi *login* gagal, dan **[Screenshot]** *Alert* Wazuh yang terpicu.

#### 4.3. Halaman Terakhir: Kesimpulan dan Manfaat

* **A. Kesimpulan:** Rangkuman hasil penerapan dan keberhasilan deteksi ancaman.
* **B. Manfaat yang Didapat:** Penjelasan mengenai wawasan dan keterampilan praktis yang diperoleh kelompok, khususnya relevansinya dengan materi Keamanan Sistem dan Jaringan Komputer.


---
By: ikhwan@fedora.linux