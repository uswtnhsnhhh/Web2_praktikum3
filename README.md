# 📚 Pemrograman Web 2 - Praktikum 3

## View Layout dan View Cell (CodeIgniter 4)

**Nama:** Muhammad Hafiyainul Yakin Wahid
**NIM:** 312410164

---

## 📌 Deskripsi

Project ini merupakan hasil dari **Praktikum 3 Pemrograman Web 2** yang berfokus pada implementasi:

* View Layout pada CodeIgniter 4
* View Cell untuk komponen modular
* Tampilan website dengan layout terstruktur dan reusable

---

## 🎯 Tujuan Praktikum

* Memahami konsep View Layout
* Menggunakan template layout agar tampilan konsisten
* Mengimplementasikan View Cell sebagai komponen dinamis
* Menampilkan data dari database ke dalam sidebar

---

## 🛠️ Teknologi yang Digunakan

* PHP (CodeIgniter 4)
* MySQL
* HTML & CSS
* XAMPP

---

## 📂 Struktur Project

```
app/
 ├── Controllers/
 ├── Models/
 │   └── ArtikelModel.php
 ├── Views/
 │   ├── layout/
 │   │   └── main.php
 │   ├── components/
 │   │   └── artikel_terkini.php
 │   └── home.php
 ├── Cells/
 │   └── ArtikelTerkini.php
public/
 └── style.css
```

---

## ⚙️ Fitur Utama

* ✅ Layout template (header, navbar, footer)
* ✅ Sidebar dengan artikel terbaru
* ✅ View Cell untuk komponen reusable
* ✅ Tampilan modern (dark mode UI)
* ✅ Data artikel dari database

---

## 🗄️ Struktur Database

### Database: `lab_ci4`

### Tabel: `artikel`

| Field      | Tipe Data |
| ---------- | --------- |
| id         | INT (PK)  |
| judul      | VARCHAR   |
| isi        | TEXT      |
| slug       | VARCHAR   |
| created_at | DATETIME  |

---

## ▶️ Cara Menjalankan Project

1. Simpan project di:

```
C:\xampp\htdocs\lab13_ci
```

2. Jalankan XAMPP (Apache & MySQL)

3. Akses di browser:

```
http://localhost/lab13_ci/public
```

---

## 🧪 Hasil Tampilan

* Halaman utama menggunakan layout
* Sidebar menampilkan **Artikel Terkini**
* UI menggunakan tema gelap (dark mode)

---

## 📸 Screenshot

![Foto](praktikum3.png)

---

## 🧠 Kesimpulan

Dengan menggunakan View Layout dan View Cell:

* Tampilan menjadi lebih rapi dan konsisten
* Kode lebih modular dan mudah digunakan kembali
* Pengembangan aplikasi menjadi lebih efisien

---

## 🚀 Catatan

Project ini dapat dikembangkan lebih lanjut dengan:

* CRUD artikel lengkap
* Halaman detail artikel
* Sistem login admin

---

