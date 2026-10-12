# Praktikum 4 --- CSS Layout

**Mata Kuliah:** Pemrograman Web\
**Nama:** Deti Kurnia\
**NIM:** 312510283\
**Repository:** `Lab4Web`

---

## 1. Tujuan Praktikum

Praktikum ini bertujuan untuk: - Memahami struktur dasar pembuatan
layout halaman web. - Memahami konsep **Box Element**, yang terdiri dari
content, padding, border, dan margin. - Memahami penggunaan CSS `float`
dan `clear`. - Mengenal elemen semantik HTML5. - Membuat halaman web
sederhana dengan header, navigasi, konten utama, sidebar, dan footer.

## 3. Langkah 1 --- Membuat Box Element

Buat dokumen HTML bernama `lab4_box.html` untuk mempelajari elemen
kotak. Tambahkan elemen `<div>` dengan kelas berbeda, misalnya `div1`,
`div2`, dan `div3`.

Contoh HTML:

```html
<section>
  <div class="div1">Div 1</div>
  <div class="div2">Div 2</div>
  <div class="div3">Div 3</div>
</section>
```

**Penjelasan:** Elemen `<div>` digunakan sebagai wadah untuk
mengelompokkan konten. Setiap kelas dapat diberi aturan CSS tersendiri
sehingga warna dan tampilannya berbeda.

**Hasil yang diharapkan:** Tiga kotak tampil pada halaman. Pada tahap
awal, kotak dapat tersusun ke bawah sebelum properti `float` diterapkan.

## 4. Langkah 2 --- CSS Float Property

Tambahkan properti `float: left` pada elemen kotak.

Contoh CSS:

```css
div {
  float: left;
  padding: 10px;
}

.div1 {
  background: red;
}

.div2 {
  background: yellow;
}

.div3 {
  background: green;
}
```

**Penjelasan:** Properti `float: left` membuat kotak mengalir ke sisi
kiri sehingga elemen dapat tersusun berdampingan. `padding` memberi
jarak antara isi kotak dan tepinya.

**Hasil yang diharapkan:** Kotak Div 1, Div 2, dan Div 3 tersusun secara
horizontal jika ruang halaman mencukupi.

**Screenshot hasil praktik:**

![Hasil CSS Float](box.png)

## 5. Langkah 3 --- Mengatur Clearfix

Tambahkan kotak keempat setelah tiga kotak sebelumnya.

```html
<div class="div4">Div 4</div>
```

Kemudian tambahkan CSS:

```css
.div4 {
  background-color: blue;
  clear: left;
  float: none;
}
```

**Penjelasan:** `clear: left` mencegah elemen berada di samping elemen
yang mengambang ke kiri. `float: none` mengembalikan elemen ke aliran
normal.

**Hasil yang diharapkan:** Div 4 berada di bawah deretan kotak yang
menggunakan `float: left`. Coba juga nilai `clear: right` dan
`clear: both`, lalu amati perbedaannya.

## 6. Langkah 4 --- Membuat Kerangka Layout

Buat file `home.html` dan hubungkan dengan `style.css`.

Bagian dasar HTML:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Layout Sederhana</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <div id="container">
      <!-- Elemen layout diletakkan di sini -->
    </div>
  </body>
</html>
```

Selanjutnya, susun elemen semantik di dalam `#container`:

```html
<header>
  <h1>Layout Sederhana</h1>
</header>

<nav>
  <a href="home.html" class="active">Home</a>
  <a href="artikel.html">Artikel</a>
  <a href="about.html">About</a>
  <a href="kontak.html">Kontak</a>
</nav>

<section id="hero"></section>

<section id="wrapper">
  <section id="main"></section>
  <aside id="sidebar"></aside>
</section>

<footer>
  <p>&copy; 2021 - Universitas Pelita Bangsa</p>
</footer>
```

**Penjelasan elemen:** - `<header>`: bagian kepala halaman. - `<nav>`:
kumpulan tautan navigasi. - `<section>`: mengelompokkan bagian konten. -
`<aside>`: konten samping atau sidebar. - `<footer>`: bagian penutup
halaman.

**Hasil yang diharapkan:** Kerangka halaman terbentuk. Tampilan akan
semakin lengkap setelah CSS dan konten ditambahkan.

**Screenshot hasil praktik:**

![Kerangka Layout](y1.png)

## 7. Langkah 5 --- Mengatur Header

Gunakan CSS berikut untuk mengatur area header:

```css
#container {
  width: 980px;
  margin: 0 auto;
  box-shadow: 0 0 1em #cccccc;
}

header {
  padding: 20px;
}

header h1 {
  margin: 20px 10px;
  color: #b5b5b5;
}
```

**Penjelasan:** `width` menentukan lebar container. `margin: 0 auto`
membuat container berada di tengah secara horizontal. `padding` memberi
ruang di dalam header, sedangkan `box-shadow` menambahkan bayangan di
sekitar container.

**Hasil yang diharapkan:** Judul "Layout Sederhana" tampil pada bagian
atas halaman dengan jarak yang cukup.

## 8. Langkah 6 --- Membuat Navigasi

Tambahkan aturan CSS untuk menu navigasi:

```css
nav {
  display: block;
  background-color: #1f5faa;
}

nav a {
  padding: 15px 30px;
  display: inline-block;
  color: #ffffff;
  font-size: 14px;
  text-decoration: none;
  font-weight: bold;
}

nav a.active,
nav a:hover {
  background-color: #2b83ea;
}
```

**Penjelasan:** Warna latar membedakan menu dari bagian lain.
`display: inline-block` membuat tautan navigasi berjajar dan tetap bisa
diberi padding. `:hover` mengubah warna ketika pointer diarahkan ke
menu, sedangkan `.active` menandai menu yang sedang aktif.

**Hasil yang diharapkan:** Menu Home, Artikel, About, dan Kontak tampil
dalam satu baris.

**Screenshot hasil praktik:**

![Navigasi](y5.png)

## 9. Langkah 7 --- Membuat Hero Panel

Isi bagian `#hero` pada `home.html`:

```html
<section id="hero">
  <h1>Hello World!</h1>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum lorem
    elit, iaculis in nisl volutpat.
  </p>
  <a href="home.html" class="btn btn-large">Learn more &raquo;</a>
</section>
```

Tambahkan CSS:

```css
#hero {
  background-color: #e4e4e5;
  padding: 50px 20px;
  margin-bottom: 20px;
}

#hero h1 {
  margin-bottom: 20px;
  font-size: 35px;
}

#hero p {
  margin-bottom: 20px;
  font-size: 18px;
  line-height: 25px;
}
```

**Penjelasan:** Hero panel adalah bagian utama yang menonjol di bawah
navigasi. Padding memberi ruang di dalam panel, sedangkan `font-size`
dan `line-height` membantu mengatur keterbacaan teks.

**Hasil yang diharapkan:** Panel berwarna abu-abu muda menampilkan
judul, paragraf, dan tautan Learn more.

**Screenshot hasil praktik:**

![Hero Panel](y0.png)

## 10. Langkah 8 --- Mengatur Main Content dan Sidebar

Tambahkan CSS berikut:

```css
#wrapper {
  margin: 0;
}

#main {
  float: left;
  width: 640px;
  padding: 20px;
}

#sidebar {
  float: right;
  width: 260px;
  padding: 20px;
}
```

**Penjelasan:** `#main` digunakan untuk konten utama, sedangkan
`#sidebar` untuk informasi tambahan di samping. Properti `float`
mengatur posisi kedua bagian. Ukuran keduanya perlu diperhatikan agar
tidak melebihi lebar container.

**Hasil yang diharapkan:** Konten utama berada di sebelah kiri dan
sidebar berada di sebelah kanan.

**Screenshot hasil praktik:**

![Main Content dan Sidebar](y11.png)

## 11. Langkah 9 --- Membuat Sidebar Widget

Contoh HTML sidebar:

```html
<aside id="sidebar">
  <div class="widget-box">
    <h3 class="title">Widget Header</h3>
    <ul>
      <li><a href="#">Widget Link</a></li>
      <li><a href="#">Widget Link</a></li>
      <li><a href="#">Widget Link</a></li>
      <li><a href="#">Widget Link</a></li>
      <li><a href="#">Widget Link</a></li>
    </ul>
  </div>

  <div class="widget-box">
    <h3 class="title">Widget Text</h3>
    <p>Konten informasi singkat pada sidebar.</p>
  </div>
</aside>
```

CSS untuk widget:

```css
.widget-box {
  border: 1px solid #eee;
  margin-bottom: 20px;
}

.widget-box .title {
  padding: 10px 16px;
  background-color: #428bca;
  color: #fff;
}

.widget-box ul {
  list-style-type: none;
}

.widget-box li {
  border-bottom: 1px solid #eee;
}

.widget-box li a {
  padding: 10px 16px;
  color: #333;
  display: block;
  text-decoration: none;
}

.widget-box li:hover a {
  background-color: #eee;
}

.widget-box p {
  padding: 15px;
  line-height: 25px;
}
```

**Penjelasan:** Widget mengelompokkan tautan dan informasi tambahan.
Border membatasi widget, judul diberi warna latar, dan efek hover
memberi respons visual saat tautan diarahkan pointer.

**Hasil yang diharapkan:** Sidebar menampilkan kotak Widget Header dan
Widget Text.

**Screenshot hasil praktik:**

![Sidebar Widget](y7.png)

## 12. Langkah 10 --- Mengatur Footer

Tambahkan CSS:

```css
footer {
  clear: both;
  background-color: #1d1d1d;
  padding: 20px;
  color: #eee;
}
```

**Penjelasan:** Footer menjadi bagian penutup halaman. `clear: both`
membuat footer berada di bawah elemen yang menggunakan float dari sisi
kiri maupun kanan.

**Hasil yang diharapkan:** Footer berwarna gelap tampil di bagian paling
bawah dengan teks yang kontras.

## 13. Langkah 11 --- Menambahkan Box Content

Tambahkan tiga kotak konten ke dalam `#main`:

```html
<section id="main">
  <div class="row">
    <div class="box">
      <img
        src="https://dummyimage.com/120/db7d25/fff.png"
        alt="Ilustrasi konten satu"
        class="image-circle"
      />
      <h3>Heading</h3>
      <p>Deskripsi singkat untuk konten pertama.</p>
      <a href="#" class="btn btn-default">View detail</a>
    </div>

    <div class="box">
      <img
        src="https://dummyimage.com/120/3e73e6/fff.png"
        alt="Ilustrasi konten dua"
        class="image-circle"
      />
      <h3>Heading</h3>
      <p>Deskripsi singkat untuk konten kedua.</p>
      <a href="#" class="btn btn-default">View detail</a>
    </div>

    <div class="box">
      <img
        src="https://dummyimage.com/120/71e6d4/fff.png"
        alt="Ilustrasi konten tiga"
        class="image-circle"
      />
      <h3>Heading</h3>
      <p>Deskripsi singkat untuk konten ketiga.</p>
      <a href="#" class="btn btn-default">View detail</a>
    </div>
  </div>
</section>
```

Tambahkan CSS:

```css
.box {
  display: block;
  float: left;
  width: 33.333333%;
  box-sizing: border-box;
  padding: 0 10px;
  text-align: center;
}

.box h3 {
  margin: 15px 0;
}

.box p {
  line-height: 20px;
  font-size: 14px;
  margin-bottom: 15px;
}

.box img {
  border: 0;
  vertical-align: middle;
}

.image-circle {
  border-radius: 50%;
}

.row {
  margin: 0 -10px;
  box-sizing: border-box;
}

.row:after,
.row:before,
.entry:after,
.entry:before {
  content: "";
  display: table;
}

.row:after,
.entry:after {
  clear: both;
}
```

**Penjelasan:** Setiap `.box` memiliki lebar sepertiga baris.
`text-align: center` meratakan isi ke tengah, sedangkan
`border-radius: 50%` membuat gambar berbentuk lingkaran. Pseudo-element
pada `.row` membantu membersihkan float.

**Hasil yang diharapkan:** Tiga kotak konten tampil sejajar dengan
gambar, judul, deskripsi, dan tautan.

## 14. Langkah 12 --- Menambahkan Artikel

Tambahkan dua elemen artikel pada bagian `#main`:

```html
<hr class="divider" />

<article class="entry">
  <h2>First featurette heading.</h2>
  <img
    src="https://dummyimage.com/150/7b8a70/fff.png"
    alt="Ilustrasi artikel pertama"
  />
  <p>Paragraf artikel pertama ditampilkan di samping gambar.</p>
</article>

<hr class="divider" />

<article class="entry">
  <h2>Second featurette heading.</h2>
  <img
    src="https://dummyimage.com/150/7b8a70/fff.png"
    alt="Ilustrasi artikel kedua"
    class="right-img"
  />
  <p>
    Paragraf artikel kedua ditampilkan dengan posisi gambar di sebelah kanan.
  </p>
</article>
```

Tambahkan CSS:

```css
.divider {
  border: 0;
  border-top: 1px solid #eee;
  margin: 40px 0;
}

.entry {
  margin: 15px 0;
}

.entry h2 {
  margin-bottom: 20px;
}

.entry p {
  line-height: 25px;
}

.entry img {
  float: left;
  border-radius: 5px;
  margin-right: 15px;
}

.entry .right-img {
  float: right;
}
```

**Penjelasan:** Elemen `<article>` digunakan untuk membungkus konten
artikel. Garis pemisah membedakan artikel, `float: left` menempatkan
gambar pertama di kiri, dan kelas `.right-img` menempatkan gambar kedua
di kanan.

**Hasil yang diharapkan:** Dua artikel tampil dengan posisi gambar yang
berbeda.

**Screenshot hasil praktik:**

![Konten Artikel](y6.png)

## 15. Tugas About dan Contact

Modul meminta penambahan halaman About dan Contact. Pada file
`home.html` yang disediakan, tautan menu sudah tersedia, tetapi file
halaman terpisah perlu dibuat agar tautan dapat dibuka.

### A. Halaman About

Buat file `about.html` yang berisi deskripsi singkat, profil, atau
portfolio. Gunakan struktur HTML dasar dan tautkan `style.css` jika
ingin memakai gaya yang sama.

**Screenshot hasil praktik:**

![Halaman About](bout.png)

### B. Halaman Contact

Buat file `kontak.html` yang berisi formulir kontak, misalnya nama,
email, dan pesan.

Contoh elemen formulir:

```html
<form>
  <label for="nama">Nama</label>
  <input type="text" id="nama" name="nama" />

  <label for="email">Email</label>
  <input type="email" id="email" name="email" />

  <label for="pesan">Pesan</label>
  <textarea id="pesan" name="pesan"></textarea>

  <button type="submit">Kirim</button>
</form>
```

**Penjelasan:** Formulir digunakan untuk mengumpulkan masukan dari
pengunjung. Contoh ini baru membuat tampilan formulir; agar pesan
benar-benar terkirim, diperlukan pemrosesan tambahan.

**Screenshot hasil praktik:**

![Halaman Contact](kontak.png)

## 17. Kesimpulan

Melalui Praktikum 4, saya mempelajari cara membangun layout web
sederhana menggunakan HTML dan CSS. Saya memahami penggunaan Box
Element, `float`, `clear`, elemen semantik HTML5, navigasi, hero panel,
main content, sidebar, widget, artikel, serta footer. Saya juga
mempelajari pentingnya menguji halaman di browser dan memvalidasi
dokumen HTML agar struktur halaman lebih baik.
