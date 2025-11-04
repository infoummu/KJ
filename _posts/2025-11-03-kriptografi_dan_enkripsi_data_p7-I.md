---
title: 🔐 Konsep Dasar Kriptografi dan Enkripsi Data P-8 - I
category: Materi
author: Ikhwan Elyas
published: true
description: Pertemuan ini membahas fundamental Kriptografi. Mahasiswa akan memahami konsep Plaintext, Ciphertext, serta tujuan utama keamanan (Kerahasiaan, Integritas). Modul ini juga menjelaskan dua metode utama Enkripsi data - Simetris (satu kunci, cepat) dan Asimetris (dua kunci, lebih aman), menyiapkan dasar untuk studi algoritma kriptografi.
---

Pertemuan ini membahas fundamental Kriptografi. Mahasiswa akan memahami konsep Plaintext, Ciphertext, serta tujuan utama keamanan (Kerahasiaan, Integritas). Modul ini juga menjelaskan dua metode utama Enkripsi data - Simetris (satu kunci, cepat) dan Asimetris (dua kunci, lebih aman), menyiapkan dasar untuk studi algoritma kriptografi.

## 🔒 Pendahuluan: Kenapa Kita Butuh Kriptografi?

Kali ini kita akan membahas topik yang sangat keren dan penting dalam keamanan: **Kriptografi** dan **Enkripsi Data**.

Bayangkan kamu mengirim surat rahasia. Agar isinya tidak dibaca orang lain di jalan, kamu pasti ingin mengubah tulisannya menjadi kode yang hanya kamu dan penerima yang tahu cara membacanya, kan? Nah, itulah ide dasar dari kriptografi!

**Kriptografi** berasal dari bahasa Yunani:
* ***Kryptos***: Tersembunyi/Rahasia
* ***Graphein***: Menulis

Jadi, **Kriptografi** adalah **ilmu dan seni untuk menjaga kerahasiaan informasi** (data) dengan cara mengubahnya menjadi format yang tidak bisa dimengerti oleh pihak yang tidak berhak.

---

## 📜 Konsep Dasar Kriptografi

Kriptografi memiliki empat (4) tujuan utama yang dikenal sebagai **CIA Triad** (Confidentiality, Integrity, Availability) ditambah dengan **Non-Repudiation**:

1.  **Kerahasiaan (*Confidentiality*)**:
    * Memastikan data hanya bisa diakses oleh pihak yang berhak.
    * **Contoh**: Mengubah data (*enkripsi*) agar tidak bisa dibaca.

2.  **Integritas (*Integrity*)**:
    * Memastikan data **belum diubah** atau **dirusak** selama proses pengiriman atau penyimpanan.
    * **Contoh**: Menggunakan *hashing* atau *digital signature* untuk mengecek keaslian data.

3.  **Otentikasi (*Authentication*)**:
    * Memastikan bahwa pengirim atau penerima adalah benar-benar pihak yang mereka klaim (asli).
    * **Contoh**: Verifikasi *password*, PIN, atau sidik jari.

4.  **Nir-Penyangkalan (*Non-Repudiation*)**:
    * Memastikan bahwa pengirim **tidak bisa menyangkal** telah mengirim pesan tersebut.
    * **Contoh**: Menggunakan *Digital Signature* yang sah secara hukum.

---

## 🔐 Memahami Enkripsi dan Dekripsi

**Enkripsi** adalah proses utama dalam kriptografi.

| Istilah | Penjelasan Sederhana |
| :--- | :--- |
| **Plaintext** | **Pesan Asli** yang mudah dibaca. (*Contoh: "Halo Dunia"*) |
| **Ciphertext** | **Pesan Terenkripsi** (kode) yang tidak bisa dibaca. (*Contoh: "kdgr qxqld"*) |
| **Enkripsi** | Proses mengubah **Plaintext** menjadi **Ciphertext**. |
| **Dekripsi** | Proses mengubah **Ciphertext** kembali menjadi **Plaintext**. |
| **Algoritma** | **Rumus/Langkah** yang digunakan untuk proses Enkripsi dan Dekripsi. |
| **Kunci (*Key*)** | **Nilai Rahasia** yang dimasukkan ke dalam Algoritma untuk mengamankan data. Kunci sangat penting! |

### 🛠️ Proses Enkripsi dan Dekripsi

$$\text{Plaintext} + \text{Kunci} \xrightarrow[\text{Algoritma}]{} \text{Ciphertext}$$
$$\text{Ciphertext} + \text{Kunci} \xrightarrow[\text{Algoritma}]{} \text{Plaintext}$$

> **Analogi Kunci dan Gembok:** Kunci (*Key*) adalah anak kunci, Algoritma adalah mekanime gemboknya. Tanpa anak kunci yang benar, gembok (enkripsi) tidak bisa dibuka!



---

## 🔑 Jenis-Jenis Enkripsi

Dalam kriptografi, ada dua (2) jenis utama sistem enkripsi berdasarkan penggunaan kuncinya:

### 1. Kriptografi Simetris (*Symmetric Cryptography*)

* **Apa itu?**: Menggunakan **KUNCI YANG SAMA** untuk proses **Enkripsi** maupun **Dekripsi**.
* **Keunggulan**: Lebih **cepat** dan efisien untuk mengenkripsi data dalam jumlah besar.
* **Kelemahan**: Sulit dalam hal **pertukaran kunci** secara aman antara pengirim dan penerima.
* **Algoritma Populer**: **AES** (*Advanced Encryption Standard*), **DES** (*Data Encryption Standard*).

$$\text{Kunci Enkripsi} = \text{Kunci Dekripsi}$$
🔑 ➜ ✉️ → 🔒


### 2. Kriptografi Asimetris (*Asymmetric Cryptography*)

* **Apa itu?**: Menggunakan **DUA KUNCI** yang berbeda tetapi saling berhubungan:
    * **Kunci Publik (*Public Key*)**: Boleh disebarkan ke siapa saja, digunakan untuk **Enkripsi**.
    * **Kunci Pribadi (*Private Key*)**: Harus **dirahasiakan**, hanya digunakan untuk **Dekripsi**.
* **Keunggulan**: **Pertukaran kunci lebih aman** dan mendukung tujuan *Otentikasi* dan *Non-Repudiation*.
* **Kelemahan**: Lebih **lambat** daripada simetris karena algoritmanya lebih kompleks.
* **Algoritma Populer**: **RSA** (*Rivest–Shamir–Adleman*), **ECC** (*Elliptic Curve Cryptography*).

$$\text{Kunci Enkripsi} \ne \text{Kunci Dekripsi}$$
🔑 ➜ ✉️ → 🔒


---

## 🤯 Latihan & Diskusi Singkat

1.  Jelaskan dengan bahasamu sendiri, apa perbedaan utama antara **Plaintext** dan **Ciphertext**?
2.  Menurutmu, manakah yang lebih cocok digunakan untuk mengenkripsi *file* besar di *hard drive*-mu: **Simetris** atau **Asimetris**? Jelaskan alasannya!
3.  Bagaimana kriptografi dapat membantu mencapai tujuan **Integritas** data? (Petunjuk: Bukan hanya enkripsi)

---

## ✅ Rangkuman

* **Kriptografi** adalah ilmu untuk mengamankan data.
* Tujuan utama: **Kerahasiaan, Integritas, Otentikasi, dan Non-Repudiation**.
* **Enkripsi** mengubah data (*Plaintext*) menjadi kode (*Ciphertext*) menggunakan **Kunci** dan **Algoritma**.
* **Simetris** menggunakan **satu kunci** (cepat, tapi pertukaran kunci sulit).
* **Asimetris** menggunakan **dua kunci** (publik dan privat) (lebih aman, tapi lebih lambat).



Sekitan dan Terima Kasih 🙏


---
by: IkhwanElyas@fedora.linux