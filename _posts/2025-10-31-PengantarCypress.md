---
title: "Pengantar Cypress"
date: 2025-10-31 15:40:00 +0800
categories: [SoftwareTesting]
tags: [Cypress, EndToEndTesting, AutomationTesting, QA, WebTesting, SDLC]
---

# Pengantar Cypress

## Apa Itu Cypress?

**Cypress** adalah framework **end-to-end testing (E2E)** yang digunakan untuk menguji aplikasi web modern seperti **React**, **Vue**, **Angular**, dan framework berbasis JavaScript lainnya.  
Framework ini dirancang untuk membantu pengembang melakukan pengujian aplikasi dari perspektif pengguna — memastikan setiap fitur, interaksi, dan halaman berjalan dengan baik di browser.

Cypress menempati posisi di antara tiga jenis pengujian utama dalam *Software Testing Life Cycle (STLC)*:

| Level Pengujian | Penjelasan | Posisi Cypress |
|------------------|-------------|----------------|
| **Unit Testing** | Menguji fungsi kecil secara terpisah | Bisa dilakukan di Cypress |
| **Integration Testing** | Menguji interaksi antar komponen | Bisa dilakukan di Cypress |
| **End-to-End Testing** | Menguji seluruh alur aplikasi dari awal hingga akhir | **Fokus utama Cypress** |

> Jadi, Cypress berperan sebagai framework **serbaguna**, tetapi paling kuat di area **End-to-End Testing**.

---

## Mengapa Cypress Populer?

Cypress berbeda dari framework testing tradisional seperti Selenium karena memiliki **arsitektur modern** dan berbagai keunggulan yang mempermudah pengujian berbasis browser.

### 🔹 Keunggulan Utama Cypress

1. **Arsitektur Modern**
   - Cypress berjalan langsung di dalam browser menggunakan JavaScript.
   - Tidak bergantung pada WebDriver eksternal seperti Selenium, sehingga lebih cepat dan stabil.

2. **Test Runner Interaktif**
   - Menampilkan hasil pengujian secara real-time.
   - Pengguna dapat melihat setiap langkah test, screenshot, dan video eksekusi.

3. **Time Travel**
   - Cypress menyimpan *snapshot* dari setiap langkah test.
   - Pengguna bisa menelusuri kembali status DOM pada setiap tahap pengujian.

4. **Automatic Waits**
   - Cypress otomatis menunggu elemen tersedia sebelum menjalankan langkah berikutnya.
   - Mengurangi kebutuhan *manual wait* atau `sleep()`.

5. **Kemudahan Penggunaan**
   - Sintaks mirip dengan bahasa alami pengguna (seperti jQuery).
   - Mudah dibaca dan dipahami bahkan oleh pemula di bidang testing.

6. **Integrasi CI/CD**
   - Dapat diintegrasikan dengan pipeline seperti Jenkins, GitHub Actions, dan GitLab CI.

---

## Persiapan Instalasi Cypress

Sebelum menggunakan Cypress, pastikan sistem memiliki **Node.js** dan **npm (Node Package Manager)**.  
Kemudian ikuti langkah-langkah instalasi berikut:

### 1️⃣ Inisialisasi Proyek
```bash
npm init -y
````

### 2️⃣ Instal Cypress

```bash
npm install cypress --save-dev
```

### 3️⃣ Membuka Cypress

```bash
npx cypress open
```

Perintah ini akan membuka *Cypress Test Runner* interaktif di browser.

### 4️⃣ Menjalankan Tes di Browser Tertentu

```bash
npx cypress run --browser chrome
npx cypress run --browser firefox
npx cypress run --browser edge
```

---

## Perintah Dasar Cypress

Berikut beberapa perintah penting yang sering digunakan dalam pembuatan *test case* Cypress:

| Perintah              | Fungsi                                    | Contoh                                     |
| --------------------- | ----------------------------------------- | ------------------------------------------ |
| `cy.visit('URL')`     | Membuka halaman web tertentu              | `cy.visit('https://example.com')`          |
| `cy.get('selector')`  | Mengambil elemen berdasarkan selector CSS | `cy.get('#username')`                      |
| `cy.type('text')`     | Mengetik teks ke dalam input field        | `cy.get('#username').type('admin')`        |
| `cy.click()`          | Klik tombol atau link                     | `cy.get('#login-button').click()`          |
| `cy.contains('text')` | Mencari elemen berdasarkan teks           | `cy.contains('Logout')`                    |
| `cy.url()`            | Mengambil URL aktif                       | `cy.url().should('include', '/dashboard')` |

Perintah-perintah ini memudahkan pengujian UI (User Interface) yang meniru perilaku pengguna nyata.

---

## Contoh Kasus: Pengujian Login di SauceDemo

Sebagai studi kasus, kita dapat melakukan pengujian login menggunakan Cypress pada situs [saucedemo.com](https://www.saucedemo.com/).

### Contoh Script:

```javascript
describe('Login Test - SauceDemo', () => {
  it('Login Berhasil dengan Kredensial Valid', () => {
    cy.visit('https://www.saucedemo.com/');
    cy.get('#user-name').type('standard_user');
    cy.get('#password').type('secret_sauce');
    cy.get('#login-button').click();
    cy.url().should('include', '/inventory.html');
  });

  it('Login Gagal dengan Kredensial Salah', () => {
    cy.visit('https://www.saucedemo.com/');
    cy.get('#user-name').type('wrong_user');
    cy.get('#password').type('wrong_pass');
    cy.get('#login-button').click();
    cy.contains('Epic sadface').should('be.visible');
  });
});
```

**Penjelasan:**

* Tes pertama memverifikasi **login valid** berhasil dan pengguna diarahkan ke halaman *Inventory*.
* Tes kedua memverifikasi **login gagal** ketika data salah dimasukkan, dan muncul pesan error yang sesuai.

---

## Kelebihan Cypress Dibanding Selenium atau Playwright

| Aspek              | Cypress                          | Selenium                      | Playwright            |
| ------------------ | -------------------------------- | ----------------------------- | --------------------- |
| Bahasa Utama       | JavaScript                       | Banyak (Python, Java, C#, JS) | JavaScript/TypeScript |
| Kecepatan Eksekusi | Sangat cepat (real-time browser) | Lebih lambat (via WebDriver)  | Cepat                 |
| Test Runner Visual | ✅ Ya (GUI interaktif)            | ❌ Tidak                       | ✅ Ya                  |
| Time Travel        | ✅ Ada                            | ❌ Tidak                       | ✅ Ada                 |
| Automatic Wait     | ✅ Ada                            | ❌ Tidak                       | ✅ Ada                 |
| Setup              | Mudah (npm install)              | Lebih kompleks                | Mudah                 |
| Fokus              | Web Modern (Frontend)            | Semua platform web            | Web & API             |

Cypress unggul untuk pengujian web modern berbasis JavaScript karena eksekusi real-time dan pengalaman visualnya yang intuitif.

---

## Test Case dan Live Coding

### Contoh Test Case

| ID Test   | Deskripsi      | Langkah                            | Hasil yang Diharapkan           |
| --------- | -------------- | ---------------------------------- | ------------------------------- |
| **TC-01** | Login berhasil | Input kredensial benar, klik Login | Berhasil masuk ke halaman utama |
| **TC-02** | Login gagal    | Input username/password salah      | Muncul pesan error              |

**Penjelasan:**

* TC-01 memastikan fungsi login bekerja sesuai skenario positif.
* TC-02 memastikan sistem menampilkan error untuk kredensial yang tidak valid.

---

## Kesimpulan

**Cypress** adalah framework **testing modern** yang sangat cocok digunakan untuk pengujian **end-to-end aplikasi web**.
Beberapa alasan mengapa Cypress menjadi pilihan populer antara lain:

* Instalasi mudah dan cepat menggunakan npm.
* Dapat dijalankan langsung di berbagai browser.
* Dilengkapi fitur unggulan seperti:

  * **Test Runner interaktif**
  * **Time Travel debugging**
  * **Automatic Waits**
* Memiliki struktur dan sintaks sederhana yang mudah dipahami.
* Mampu meniru perilaku pengguna sebenarnya dengan sangat baik.

Melalui studi kasus pengujian login di *saucedemo.com*, Cypress terbukti efektif untuk:

* Menguji skenario positif dan negatif.
* Memastikan keandalan dan kualitas aplikasi web secara keseluruhan.

> Dengan kombinasi kecepatan, kemudahan, dan kejelasan hasil, **Cypress** menjadi salah satu alat terbaik dalam pengujian UI otomatis saat ini.

---

*Disusun oleh:*
**Kelompok 8 STQA Sistem Informasi 2023 – Universitas Hasanuddin**
Nurul Wahdania, Dhian Alifka Azzahra, Rohsilia Gratia Simak, Rayhan Jahzari, Muhammad Nuzil Alfikri, Kevin Ardhana, Restu Ahmadinata, A. Muhammad Zulfikar, dan Ahmad Rafly Putra Hasrun.