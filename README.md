# Pemrograman Web 2 - Praktikum 3

## View Layout dan View Cell (CodeIgniter 4)

**Nama:** **Uswatun Hasanah**

**NIM:** **312410163**

---

## Deskripsi

Project ini merupakan hasil dari **Praktikum 3 Pemrograman Web 2** yang berfokus pada implementasi:

* View Layout pada CodeIgniter 4
* View Cell untuk komponen modular
* Tampilan website dengan layout terstruktur dan reusable

---

## Tujuan Praktikum

* Membuat template utama website
* Menggunakan View Layout pada CodeIgniter 4
* Menggunakan extend() dan section()
* Membuat View Cell
* Menampilkan artikel terbaru pada sidebar
* Membuat tampilan website lebih rapi dan terstruktur

---

## Tahapan Pengerjaan

1. Membuat Layout Utama
  Membuat Folder:
```
app/Views/layout
```
  Lalu membuat folder:
```
app/Views/layout/main.php
```
File ini digunakan sebagai template utama yang berisi:

* Header
* Navbar
* Main Content
* Sidebar
* Footer

Contoh bagian utama:
```
<?= $this->renderSection('content') ?>
```
Bagian ini digunakan untuk menampilkan isi halaman dari view lain.

2. Membuat Home View dengan Extend Layout
  Membuat file:
```
app/Views/home.php
```
  Isi file:
 ```
<?= $this->extend('layout/main') ?>

<?= $this->section('content') ?>

<h1><?= $title; ?></h1>
<hr>
<p><?= $content; ?></p>

<?= $this->endSection() ?>
```
Fungsi extend() digunakan agar halaman Home memakai template utama dari layout/main.php.

3. Mengubah Home Controller
  File:
```
app/Controllers/Home.php
```
  Diubah menjadi:
```
<?php

namespace App\Controllers;

class Home extends BaseController
{
    public function index()
    {
        $data = [
            'title'   => 'Home',
            'content' => 'Selamat datang di Website Artikel menggunakan CodeIgniter 4'
        ];

        return view('home', $data);
    }
}
```
Controller ini digunakan untuk menampilkan halaman Home menggunakan layout baru.

4. Membuat View Cell
  Membuat folder:
```
app/Cells
```
  Lalu membuat file:
```
app/Cells/ArtikelTerkini.php
```
  Isi file:
```
<?php

namespace App\Cells;

use App\Models\ArtikelModel;

class ArtikelTerkini
{
    public function render()
    {
        $model = new ArtikelModel();

        $artikel = $model->orderBy('id', 'DESC')
                         ->limit(5)
                         ->findAll();

        return view('components/artikel_terkini', [
            'artikel' => $artikel
        ]);
    }
}
```
View Cell ini digunakan untuk menampilkan daftar artikel terbaru pada sidebar.

5. Membuat View Component
  Membuat folder:
```
app/Views/components
```
  Lalu membuat file:
```
app/Views/components/artikel_terkini.php
```
  Isi file:
```
<h3>Artikel Terkini</h3>

<ul>
<?php foreach ($artikel as $row): ?>
    <li>
        <a href="<?= base_url('/artikel/' . $row['slug']) ?>">
            <?= $row['judul'] ?>
        </a>
    </li>
<?php endforeach; ?>
</ul>
```
File ini akan dipanggil oleh View Cell dan ditampilkan pada sidebar.

6. Menambahkan View Cell ke Layout
  Pada file:
```
app/Views/layout/main.php
```
  ditambahkan:
```
<?= view_cell('App\\Cells\\ArtikelTerkini::render') ?>
```
Tujuannya agar artikel terbaru muncul otomatis pada sidebar.



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

## Hasil Praktikum
  Berhasil menampilkan:
* Layout utama website
* Header
* Navigation bar
* Sidebar kanan
* Artikel terkini otomatis
* Footer
* Halaman Home dengan template layout
* Halaman Artikel dari database

URL akses:
```
http://localhost/lab11_php_ci/ci4/public/
```
Halaman artikel:
```
http://localhost/lab11_php_ci/ci4/public/artikel
```

---

## 🧪 Hasil Tampilan

* Halaman utama menggunakan layout
* Sidebar menampilkan **Artikel Terkini**

---

## 📸 Screenshot

(<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/96fa7ca9-e645-4026-974e-fc83dcf5cd1b" />)
(<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/e2c6f7e2-0adf-4f8d-949c-de3eb6bfe508" />)


---

## Kesimpulan

Pada Modul 3 berhasil dibuat layout utama website menggunakan View Layout dan komponen dinamis menggunakan View Cell. Dengan penerapan ini, struktur tampilan website menjadi lebih rapi, konsisten, dan mudah dikembangkan untuk modul selanjutnya seperti CRUD artikel.

---


