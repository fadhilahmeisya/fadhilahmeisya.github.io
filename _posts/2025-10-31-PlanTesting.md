---
title: "Plan Testing"
date: 2025-10-31 10:30:00 +0800
categories: [SoftwareTesting]
tags: [TestPlan, QA, SDLC, SoftwareTesting]
---

## Pengantar

**Testing Plan** atau **Rencana Pengujian** adalah dokumen panduan yang menjelaskan bagaimana proses pengujian perangkat lunak akan dilakukan.  
Dokumen ini berisi informasi penting seperti ruang lingkup pengujian, strategi yang digunakan, sumber daya yang diperlukan, serta jadwal pelaksanaan.

Testing Plan berfungsi sebagai acuan resmi bagi tim penguji agar kegiatan pengujian lebih **terarah, efisien, dan konsisten**.

---

## Tujuan Testing Plan

Rencana pengujian bertujuan untuk:

- Menyediakan gambaran yang jelas tentang **apa yang diuji** dan **bagaimana cara mengujinya**.  
- Menemukan sebanyak mungkin kesalahan sebelum perangkat lunak dirilis.  
- Memastikan software mencapai **kualitas yang dapat diterima pengguna**.  
- Mengoptimalkan penggunaan **waktu, biaya, dan tenaga**.  
- Memberikan dokumentasi yang dapat dijadikan **referensi proyek berikutnya**.

---

## Komponen dalam Testing Plan

Menurut **standar IEEE 829-1988**, sebuah dokumen *test plan* idealnya mencakup beberapa komponen penting berikut.

---

### 1. Plan Identifier
Kode atau nomor versi unik yang digunakan untuk membedakan test plan antar proyek atau versi.  
**Fungsi:**  
- Memudahkan pengelolaan dokumen dan revisi.  
- Menjadi referensi saat terjadi perubahan.  

---

### 2. References
Daftar dokumen, standar, atau sumber yang digunakan sebagai acuan dalam penyusunan test plan.  
**Fungsi:**  
- Memastikan konsistensi dengan dokumen utama proyek.  
- Mendukung validitas hasil pengujian.

---

### 3. Introduction
Bagian pembuka yang menjelaskan tujuan, ruang lingkup, dan fokus pengujian.  
**Fungsi:** Memberikan gambaran umum kepada stakeholder tentang arah pengujian sebelum masuk ke detail teknis.

---

### 4. Test Items
Daftar komponen, fitur, modul, atau artefak perangkat lunak yang **akan diuji** dalam proses pengujian.

---

### 5. Software Risk Issues
Mengidentifikasi risiko yang mungkin muncul selama pengujian, seperti:  
- Fitur baru atau kompleks.  
- Integrasi antar versi perangkat lunak.  
- Kebutuhan yang ambigu.  
- Kesalahpahaman terhadap spesifikasi.  

Tujuannya adalah menyiapkan langkah pencegahan dan penanganan yang tepat.

---

### 6. Features to be Tested
Menjelaskan fitur atau fungsi yang akan diuji dari perspektif pengguna.  
Berbeda dari *Test Items* yang bersifat teknis, bagian ini berfokus pada **kegunaan dan risiko pengguna akhir**.

---

### 7. Features Not to be Tested
Daftar fitur yang **tidak termasuk dalam pengujian**, beserta alasannya.  
Biasanya karena:
- Fitur sudah stabil atau sering digunakan.  
- Tidak termasuk dalam versi rilis saat ini.  

---

### 8. Approach (Pendekatan Pengujian)
Menjelaskan **strategi umum** yang digunakan, meliputi:
- **Jenis testing:** Unit, Integration, System, atau Acceptance.  
- **Metode testing:** Manual atau otomatis.  
- **Teknik testing:** Black-box, White-box, atau Gray-box.  
- **Tujuan testing:** Validasi fungsionalitas, kinerja, atau keamanan.

---

### 9. Item Pass/Fail Criteria
Menetapkan kriteria yang menentukan apakah suatu pengujian **lulus** atau **gagal**.

- **Pass Criteria:** Semua test case berjalan sesuai harapan, tanpa bug kritis.  
- **Fail Criteria:** Ada test case gagal, atau ditemukan defect mayor yang memengaruhi fungsi utama.

Kriteria ini menjaga evaluasi tetap **objektif dan konsisten**.

---

### 10. Suspension Criteria & Resumption Requirements
- **Suspension Criteria:** Kondisi di mana pengujian harus dihentikan sementara (misalnya ditemukan bug kritis).  
- **Resumption Requirements:** Syarat yang harus dipenuhi sebelum pengujian dilanjutkan kembali, memastikan masalah sudah diperbaiki.

---

### 11. Test Deliverables
Dokumen dan hasil nyata dari proses pengujian, seperti:  
- Test Plan, Test Case, dan Hasil Eksekusi.  
- Laporan bug dan ringkasan pengujian (*Test Summary Report*).  
Menjadi bukti bahwa pengujian telah dilakukan dengan baik.

---

### 12. Remaining Test Tasks
Daftar pekerjaan yang belum selesai pada saat laporan dibuat, serta langkah yang perlu dilakukan sebelum fase pengujian ditutup.

---

### 13. Environmental Needs
Menjelaskan **lingkungan pengujian** yang dibutuhkan:  
- Spesifikasi hardware dan software.  
- Data uji dan kredensial akses.  
- Konfigurasi jaringan dan alat pendukung.

Lingkungan yang tepat menjamin hasil pengujian dapat direproduksi.

---

### 14. Responsibilities
Menjelaskan pembagian tugas dan tanggung jawab:  
- Siapa yang menulis dan menjalankan test case.  
- Siapa yang memverifikasi bug dan mengambil keputusan.  
Struktur pelaporan dan jalur eskalasi juga dijelaskan agar koordinasi lebih efektif.

---

### 15. Staffing and Training Needs
Menjelaskan kebutuhan personel dan pelatihan yang diperlukan, seperti:  
- Peran utama: Test Manager, Tester, Developer, Tim Operasi.  
- Kompetensi yang dibutuhkan.  
Termasuk sesi *cross-training* agar tidak bergantung pada satu individu.

---

### 16. Schedule
Menetapkan jadwal lengkap kegiatan pengujian, mulai dari:  
- Persiapan dan review test case.  
- Eksekusi dan retest.  
- Penutupan dan sign-off rilis.  
Juga mencakup *milestone* penting dan ketergantungan antar tim.

---

### 17. Glossary
Berisi definisi istilah teknis seperti *Test Items*, *Pass Criteria*, atau *Software Risk Issues* untuk memastikan semua pihak memiliki pemahaman yang sama.

---

### 18. Approvals
Memuat daftar pihak yang menyetujui dokumen test plan, biasanya mencakup:  
- Nama dan jabatan.  
- Tanda tangan dan tanggal persetujuan.

---

## Kesimpulan

**Testing Plan** merupakan fondasi penting dalam manajemen pengujian perangkat lunak.  
Dengan rencana yang matang, tim penguji dapat bekerja secara terstruktur, menghindari miskomunikasi, dan memastikan hasil pengujian yang akurat serta terukur.

Rencana pengujian yang baik bukan hanya panduan teknis, melainkan juga alat komunikasi antara tim teknis, manajemen, dan stakeholder untuk menjamin keberhasilan proyek.

---

*Disusun oleh:*  
**Kelompok 3 Sistem Informasi 2023**  
Alifsa Rezky Rahmah S, Rezka Wildan Nurhadi Bakri, Muh. Aipun Pratama, Muhammad Raihan,  
An Naura Erwana Dwi Putri, Resky Auliyah Kartini A, Roland Philip Boli K, Chandra Junardi Tandirerung.
