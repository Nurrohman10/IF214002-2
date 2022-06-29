## APLIKASI BUKU ONLINE
#### Deskripsi
aplikasi ini dirancang untuk mempermudah pembaca buku secara online. beberapa fitur-fiutr yang tersedia diantaranya :
  - Semua koleksi bahan bacaan dalam satu aplikasi
  - berbagai cerita menarik lainnya
  - fitur optimasi layar untuk membaca
  - perpustakaan bacaan
  - navigasi
  - bookmark
  - table of contens

## Entitas dan Atribut
### Admin
- Id_admin
- nama_admin
- Pass_admin
- gender_admin
- email_admin

### User
- id_user
- nama_user
- pass_user
- gender_user
- email_user
- register

### buku
- id_buku
- nama_buku
- is_tamat
- is_terbaik
- is_terbaru
- id_author
- id_user

### olahdata
- id_admin
- id_user
- data_buku
### baca
- id_user
- id_buku
- history
### author
- id_author
- nama_author
### terbaik
- is_terbaik
- views_buku

---

## ERD Aplikasi Buku
![ERD-project drawio](https://user-images.githubusercontent.com/100669802/176473084-acbd9ea2-eac0-4f59-9ca7-01ac7a233aee.png)
![ERD-project](https://user-images.githubusercontent.com/100669802/176473174-1264e9e2-37cd-465b-bd41-d5525a769c60.png)

---

- [Webservice] (https://github.com/Nurkholis070401/IF214002/blob/main/Pertemuan%2014/Webservice.php) 
- [Visualisasi Data] (https://github.com/Nurkholis070401/IF214002/blob/main/Pertemuan%2014/visualizationData.php)

