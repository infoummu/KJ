---
title: 🧾 Audit Sistem dan Analisis Log Keamanan (Linux) P-7
category: Materi
author: Ikhwan Elyas
published: true
description: Audit sistem dan analisis log keamanan di Linux berperan penting dalam memantau aktivitas sistem serta mendeteksi potensi ancaman atau penyalahgunaan. Melalui pemeriksaan log seperti login, perintah sudo, dan perubahan file, administrator dapat menilai integritas sistem, menemukan celah keamanan, dan menjaga kestabilan serta keandalan server.
---

**Tujuan Pembelajaran (studi kasus – Debian 12):**
- Setelah mengikuti pertemuan ini, mahasiswa bisa:
    1. Mengaktifkan audit log di sistem operasi Linux (Debian 12)
    2. Membaca dan memahami isi log keamanan
    3. Menggunakan perintah sederhana untuk mencari tanda-tanda mencurigakan
    4. Mengamankan server dari serangan dasar

---

## 1. Apa Itu Audit dan Log Keamanan?

| Istilah | Penjelasan Sederhana |
|---|---|
| **Log** | Catatan aktivitas sistem (seperti buku harian server) |
| **Audit** | Pencatatan khusus untuk keamanan (siapa melakukan apa, kapan) |
| **Auditd** | Program di Linux untuk mencatat aktivitas penting |

> Bayangkan kamu punya toko. Log = nota penjualan. Audit = CCTV yang merekam siapa masuk-keluar.

---

## 2. Persiapan Server Debian 12

```bash
# Update sistem dulu
sudo apt update && sudo apt upgrade -y

# Install auditd (belum ada secara default)
sudo apt install auditd audispd-plugins -y
```

Cek apakah auditd sudah jalan:

```bash
sudo systemctl status auditd
```

Jika muncul `active (running)` → sudah siap!

## 3. Mulai Menggunakan Auditd

### 3.1. Aktifkan Auditd Otomatis Saat Boot

```bash
sudo systemctl enable auditd
```

### 3.2. Tambahkan Aturan Audit (Contoh Sederhana)

Kita akan pantau:
* Perubahan file konfigurasi penting
* Login gagal
* Perintah `sudo`

```bash
# 1. Pantau file /etc/passwd dan /etc/shadow
sudo auditctl -w /etc/passwd -p wa -k passwd_changes
sudo auditctl -w /etc/shadow -p wa -k shadow_changes

# 2. Pantau login gagal
# (Aturan ini lebih kompleks, untuk pemula cukup tahu tujuannya)
# sudo auditctl -a always,exit -F arch=b64 -S execve -F path=/usr/bin/sudo -F auid>=1000 -k sudo_usage

# 3. Pantau semua perintah sudo
sudo auditctl -a always,exit -F arch=b64 -S execve -F path=/usr/bin/sudo -k sudo_commands
```

- `-w` = watch file
- `-p wa` = write & attribute change
- `-k` = beri label agar mudah dicari

## 4. Melihat Log Audit

Log audit disimpan di: `/var/log/audit/audit.log`

### 4.1. Baca Log Secara Langsung

```bash
sudo less /var/log/audit/audit.log
```

Tekan `q` untuk keluar.

### 4.2. Cari Kata Kunci (Pake ausearch)

```bash
# Cari perubahan di passwd
sudo ausearch -k passwd_changes

# Cari penggunaan sudo
sudo ausearch -k sudo_commands

# Cari login gagal (failed)
sudo ausearch -m USER_AUTH -ts today | grep "fail"
```

- `-ts today` = hanya hari ini
- `-m USER_AUTH` = tipe pesan login

## 5. Contoh Kasus Nyata (Implementatif!)

**Kasus:** Ada yang coba login gagal berkali-kali!

```bash
# Cek login gagal hari ini
sudo ausearch -m USER_AUTH -ts today --raw | grep "fail" | wc -l
```

Jika hasil > 10 → WASPADA! Mungkin serangan brute force.

## 6. Log Sistem Lain yang Penting

| File Log | Isi |
|---|---|
| `/var/log/auth.log` | Login sukses/gagal, sudo |
| `/var/log/syslog` | Semua aktivitas sistem |
| `/var/log/kern.log` | Masalah hardware/kernel |

**Perintah Cepat:**

```bash
# Lihat 20 baris terakhir login
tail -20 /var/log/auth.log

# Cari "failed password"
grep "failed password" /var/log/auth.log
```

## 7. Implementasi (Debian 12)

1. Instal dan aktifkan `auditd`
2. Tambahkan 3 aturan audit seperti di atas
3. Lakukan 3 kali login salah (sengaja salah password)
4. Gunakan `ausearch` untuk menemukan jejaknya
5. Screenshot hasilnya → kirim ke dosen

```bash
# Contoh perintah tugas
sudo ausearch -m USER_AUTH -ts today | grep "fail"
```

## 8. Tips Keamanan untuk Pemula

| Tips | Perintah |
|---|---|
| Ganti password root | `sudo passwd root` |
| Nonaktifkan login root via SSH | Edit `/etc/ssh/sshd_config` → `PermitRootLogin no` |
| Batasi login SSH | Install fail2ban: `sudo apt install fail2ban` |

## 9. Ringkasan Perintah Penting

| Perintah | Fungsi |
|---|---|
| `sudo apt install auditd` | Install audit |
| `sudo auditctl -w /file -p wa -k nama` | Pantau file |
| `sudo ausearch -k nama` | Cari log audit |
| `tail -f /var/log/auth.log` | Pantau login real-time |
| `grep "failed" /var/log/auth.log` | Cari login gagal |

---

* **Catatan:**
    * Log itu seperti jejak kaki. Kalau kamu tahu cara membacanya, kamu bisa tahu siapa yang masuk rumah (server) kamu.*
    * File ini siap di-download dan dibagikan ke mahasiswa.*
    * Dibuat khusus untuk Debian 12 dengan peserta Mahasiswa Infra.*


Sekitan dan Terima Kasih 🙏


---
by: IkhwanElyas@fedora.linux