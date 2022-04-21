## 1. Dengan menggunakan basis data, pengambilan informasi dapat dilakukan dengan cepat dan mudah. Basis data memiliki kemampuan dalam mengelompokan, mengurutkan bahkan perhitungan dengan metematika. Dengan perancangan yang benar, maka penyajian informasi akan dapat dilakukan dengan cepat dan mudah. Mengelompokkan data dan informasi sehingga lebih mudah dimengerti. Mencegah terjadinya duplikat data maupun inkonsistensi data.  - ERD adalah bentuk model untuk menyusun kerangka database untuk mempermudah dalam memberikan gambaran terkait relasi dalam bentuk sebuah desain. Untuk membuat diagram ER yang baik, anda dapat mencoba dengan menentukan entitas dan atribut yang diperlukan terkait proyek anda.

## 2. proses bisnis ke struktur data basis data. serangkaian aktifitas yang dilakukan oleh suatu bisnis dimana mencakup inisiasi input, transformasi dari suatu informasi, dan menghasilkan output. Output tersebut dapat bernilai untuk di ubah ke entitas data di sturuktur. Suatu proses bisnis dapat dipecah menjadi beberapa sub-proses yang masing-masing memiliki atribut sendiri yang berkontribusi untuk mencapai tujuan dari proses induknya, sub proses dan atribut ter sebut di ubah ke struktur basis data. Sub-proses dapat dipecah lagi menjadi aktifitas, yaitu sub-proses terkecil yang dapat terdiri dari satu atau lebih langkah (steps) yang harus dicantumkan dalam proses bisnis tersebut juga dapat di ubah ke struktur data bisis data.

# Aplikasi Baca buku (komik&novel)
## 3 Deskripsi
aplikasi ini dirancang untuk mempermudah pembaca buku secara online, dan buku yang tersedia merupakan buku komik dan novel. beberapa fitur-fiutr yang tersedia diantaranya :

- Semua koleksi bahan bacaan dalam satu aplikasi
- berbagai cerita menarik lainnya
- fitur optimasi layar untuk membaca
- menandai buku yang disukai

![Pertemuan3 drawio (1)](https://user-images.githubusercontent.com/100669802/164356211-e7a2e2ad-2142-4fcb-a641-2928a83c32f5.png)
![pertemuan5-erd drawio (6)](https://user-images.githubusercontent.com/100669802/164356374-60bef831-34d5-4f8e-8f7f-a8a3e0a60cd9.png)


## Tabel Normalisasi 1,2 dan 3

#### Tabel Admin
|🔑id_admin|nama_admin|no_hp_admin|pass_admin|Email_admin|Gender_user|
|---|---|---|---|---|---|
|1|asep kudt|087745671111|asepppus|@asepppgmail.com|Kali-laki|
|2|alip Mandalika|087899881212|alippp|@alipsndahgmail.com|Kali-laki|
|3|friday day|087899881212|afridayy|@friday.gmailcom|Kali-laki|

#### Tabel pengguna
|🔑id_user|nama_user|Pass_user|gender_user|email_user|History|Favorit|
|---|---|---|---|---|---|---|
|1|asepp kaler|asepp12|perempuan|@asepp.com|black-121222|one peace|
|2|san day|sann13|laki-laki|@sanday.com|one peace-130322|zero|
|3|ujang|ujang14|laki-laki|@ujang.com|zero-110722|black|

#### Tabel Buku
|🔑id_buku|id_author|is_terbaik|is_terbaru|is_tamat|is_favorit|
|---|---|---|---|---|---|
|1|asepp kudet|sololev|overgear|naruto|naruto|
|2|friday day|one peace|black clover|boruto|naruto|
|3|ujang|naruto|zero|war god|naruto|

#### Tabel author
|🔑id_author|nama_author|id_buku|nama_buku|
|---|---|---|---|
|1|rijal kaler|1|Overgear|
|2|tus day|2|kimetsu|
|2|tus day|2|war god|
|3|ruko|3|thunder god|

#### Tabel terbaik
|🔑is_terbaik|nama_buku|
|---|---|
|1|onepeace|
|2|zero|
|3|black clover|
