# Nama    : Muzaki Arifin
# NPM     : 4525210051
# Matkul  : [Desain Web]
# Tugas   : Landing Page Responsif – Arunika Studio


## Gambaran Umum

Proyek ini adalah landing page satu halaman untuk studio fiktif bernama **Arunika Studio** yang menawarkan jasa desain web. Halaman dibuat dengan **HTML** dan **CSS** murni (tanpa framework dan tanpa JavaScript), dan tampilannya menyesuaikan ukuran layar, baik desktop maupun ponsel.

**Struktur folder:**

```
.
├── index.html
├── css/
│   └── style.css
├── img/
│   ├── desktop.png
│   └── mobile.png
└── README.md
```

**Screenshot tampilan desktop:**

![Tampilan Desktop]
<img width="1920" height="1080" alt="ss web" src="https://github.com/user-attachments/assets/2c8ca58b-de08-48af-a9a1-490c021ec4ef" />


**Screenshot tampilan mobile:**

![Tampilan Mobile]
<img width="624" height="910" alt="ss mobile" src="https://github.com/user-attachments/assets/3ff86321-b5f6-4770-afa2-e225a01eb040" />
<img width="623" height="907" alt="ss mobile2" src="https://github.com/user-attachments/assets/a190ed02-9753-4d7b-acc1-5fb7ccc1c53a" />


---

## Bagian 01 – Struktur HTML (`index.html`)

**Penjelasan:**
- Semua isi halaman dibungkus dalam `<div class="page">`, jadi lebar dan bayangannya bisa diatur dari satu tempat.
- Halaman dibagi menjadi tiga bagian utama: `<header>`, dua `<section>` (`#hero` dan `#layanan`), dan `<footer>`.
- Menu navigasi memakai *anchor link* (`#hero`, `#layanan`, `#kontak`) yang mengarah ke `id` masing-masing bagian, sehingga klik menu akan menggulir halaman ke bagian tersebut.
- Tag `<meta name="viewport">` wajib ada supaya layout responsif bisa bekerja di ponsel.
- Atribut `lang="id"` menandakan bahwa isi halaman berbahasa Indonesia.

---

## Bagian 02 – Pengaturan Dasar (Reset dan Body)

**Penjelasan:**
- Selector `*` menghapus `margin` dan `padding` bawaan browser supaya tampilan konsisten di semua browser.
- `box-sizing: border-box` membuat lebar elemen sudah termasuk `padding` dan `border`, jadi ukuran lebih mudah dihitung.
- `body` mengatur font (`Segoe UI`), tinggi baris (`line-height: 1.6`), warna teks, dan warna latar halaman.
- `.page` dibatasi `max-width: 880px` dan diberi `margin: 0 auto` supaya berada di tengah layar. `overflow: hidden` dipakai agar sudut membulat (`border-radius`) ikut memotong isi di dalamnya.

---

## Bagian 03 – Class Reusable

**Penjelasan:**
- **`.heading`** dipakai untuk judul section (contoh: "Layanan Kami"). Ciri khasnya teks rata tengah dan garis bawah putus-putus (`dotted`).
- **`.btn`** dipakai untuk tombol ajakan ("Lihat Layanan"). Dibuat dari tag `<a>` dengan `display: inline-block` supaya bisa diberi `padding`, dan `border-radius: 50px` agar bentuknya seperti kapsul.
- Efek `:hover` pada `.btn` mengubah warna latar sehingga pengunjung tahu tombol bisa diklik.
- Karena berupa class, keduanya bisa dipakai ulang di bagian mana pun tanpa menulis CSS baru.

---

## Bagian 04 – Header dan Navigasi

**Penjelasan:**
- `header` memakai **Flexbox** (`display: flex`) dengan `justify-content: space-between`, sehingga logo ada di kiri dan menu di kanan.
- `align-items: center` membuat logo dan menu sejajar secara vertikal.
- Kata "Studio" dibungkus `<span>` di dalam `.brand` supaya bisa diberi warna berbeda dari kata "Arunika".
- Link navigasi diberi `text-decoration: none` untuk menghilangkan garis bawah, dan efek `hover` membalik warna (latar putih, teks navy) agar interaktif.

---

## Bagian 05 – Hero

**Penjelasan:**
- Bagian `#hero` berisi logo bulat, judul, deskripsi singkat, dan tombol.
- `.logo-circle` dibuat bulat dengan `width` dan `height` yang sama (90px) ditambah `border-radius: 50%`. Teks "ZZ" di dalamnya diletakkan di tengah memakai `line-height`.
- `margin: 0 auto` pada logo dan paragraf membuat keduanya berada di tengah. Paragraf juga dibatasi `max-width: 500px` agar teks tidak terlalu melebar.
- Selector `#hero h2` dan `#hero p` hanya berlaku untuk elemen di dalam hero, jadi tidak mengganggu `h2` di bagian lain.

---

## Bagian 06 – Layanan (Tiga Card)

**Penjelasan:**
- `.service-list` memakai Flexbox dengan `gap: 18px` sehingga tiga card tersusun berjajar dengan jarak yang rata.
- `flex: 1` pada `.service-card` membuat ketiga card punya lebar yang sama.
- Tiap card punya garis atas tebal (`border-top: 5px`), sudut membulat, dan badge nomor (`.number`) berbentuk kapsul kecil.
- Isi card ada tiga: **Web Design**, **Web Development**, dan **Branding**.

---

## Bagian 07 – Footer

**Penjelasan:**
- `footer` berisi alamat email (`.contact`, dicetak tebal) dan teks hak cipta.
- Warna latar footer disamakan dengan header supaya halaman terlihat seimbang dari atas ke bawah.
- Id `#kontak` pada footer menjadi tujuan dari menu "Kontak" di navigasi.

---

## Bagian 08 – Responsive (Media Query)

**Penjelasan:**
- Media query `@media (max-width: 767px)` aktif ketika lebar layar di bawah 768px (ukuran ponsel).
- Pada layar kecil: header berubah jadi **satu kolom** (`flex-direction: column`), `padding` section dikurangi, dan ukuran judul hero dikecilkan dari 32px menjadi 24px.
- Perubahan terpenting ada di `.service-list`: `flex-direction: column` membuat tiga card yang tadinya berjajar menjadi **tersusun ke bawah**, sehingga tetap nyaman dibaca di layar sempit.
- Cara mengetesnya: buka `index.html` di browser, lalu perkecil lebar jendela atau pakai mode responsive di Developer Tools (F12).

---

## Palet Warna yang Dipakai

| Warna | Kode | Dipakai untuk |
|---|---|---|
| Navy | `#0f2a4a` | Header, footer, judul, border card |
| Amber | `#f59e0b` | Tombol, badge nomor, garis putus-putus, border logo |
| Kuning muda | `#fcd34d` | Kata "Studio" pada logo |
| Biru sangat muda | `#f1f6fb` | Latar hero dan card |
| Biru keabuan | `#e8eef5` | Latar halaman |

---

## Ringkasan Properti CSS yang Dipakai

| Properti | Fungsi |
|---|---|
| `display: flex` | Menyusun elemen berjajar (header dan card layanan) |
| `justify-content` / `align-items` | Mengatur posisi horizontal dan vertikal di Flexbox |
| `gap` | Memberi jarak antar elemen dalam Flexbox |
| `box-sizing: border-box` | Lebar sudah termasuk padding dan border |
| `border-radius` | Membuat sudut membulat atau lingkaran |
| `max-width` + `margin: 0 auto` | Membatasi lebar dan menaruh elemen di tengah |
| `:hover` | Mengubah tampilan saat kursor diarahkan |
| `@media (max-width: 767px)` | Mengubah layout untuk layar ponsel |
