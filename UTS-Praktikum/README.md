## Jelaskan contoh-contoh perintah SQL beserta kegunannya !

## Perintah SELECT 
Perintah SELECT merupakan perintah dasar SQL yang di gunakan untuk memilih data dari database. Data yang di kembalikan di simpan dalam tabel yang di sebut result-set. SELECT kolom1, kolom2, … FROM nama_tabel;
SELECT * FROM nama_tabel;
## Perintah SELECT DISTINCT
Perintah SELECT DISTINCT merupakan perintah dasar SQL yang di gunakan untuk mengembalikan hanya nilai yang berbeda dari dalam sebuah tabel, dengan kata lain semua record duplikat (record dengan nilai yang sama) yang terdapat pada tabel akan di anggap sebagai satu record/nilai.
SELECT DISTINCT kolom1, kolom2, … FROM nama_tabel;
## Perintah WHERE
Perintah WHERE merupakan perintah dasar SQL yang di gunakan untuk mem-filter hasil SELECT dengan mengekstrak record yang memenuhi persyaratan tertentu.
SELECT kolom1, kolom2, … FROM nama_tabel WHERE kondisi;
## Perintah (operator) AND, OR dan NOT
Operator AND, OR dan NOT merupakan perintah dasar SQL yang biasanya di kombinasikan dengan perintah WHERE. Ketiganya di gunakan untuk mem-filter record berdasarkan suatu kondisi, operator AND akan menampilkan record apabila semua kondisi bernilai TRUE, operator OR akan menampilkan record apabila salah satu kondisi bernilai TRUE, sedangkan operator NOT akan menampilkan record apabila semua kondisi bernilai FALSE.

SELECT kolom1, kolom2, … FROM nama_tabel WHERE kondisi1 AND kondisi2 AND kondisi3;
SELECT kolom1, kolom2, … FROM nama_tabel WHERE kondisi1 OR kondisi2 OR kondisi3 …;

## Perintah ORDER BY
Perintah ORDER BY merupakan perintah dasar SQL yang di gunakan untuk mengurutkan result-set dalam pengurutan ‘ascending’ atau ‘descending’. Secara default perintah ORDER BY menampilkan record dalam pengurutan ‘ascending’ (‘ASC’). Untuk mengurutkan ‘descending’, gunakan kata kunci ‘DESC’.

SELECT kolom1, kolom2, … FROM nama_tabel ORDER BY column DESC;

SELECT nis, nama FROM siswa ORDER BY tahun_lahir DESC;

##  Perintah INSERT INTO
Dalam SQL, perintah INSERT INTO merupakan perintah dasar SQL bagian dari perintah untuk DML (Data Manipulation Language) Saya asumsikan Anda telah faham perbedaan DDL, DCL, dan DML. Perintah INSERT INTO dapat di gunakan untuk menambahkan record baru ke dalam tabel.

INSERT INTO nama_tabel VALUES (nilai1, nilai2, nilai3, …);
INSERT INTO nama_tabel (kolom1, kolom2) VALUES (nilai1, nilai2);
## Perintah UPDATE
Perintah UPDATE merupakan perintah dasar SQL yang di gunakan untuk memperbarui atau mengubah nilai suatu record berdasarkan kriteria tertentu.

UPDATE nama_tabel SET kolom1 = nilai1, kolom2 = nilai2, … WHERE kondisi;
##  Perintah DELETE
Hampir sama dengan perintah UPDATE, perintah DELETE juga merupakan perintah dasar SQL yang di gunakan untuk menghapus nilai suatu record berdasarkan kriteria tertentu.
## Normalisasi
#### Tabel Admin
|🔑id_admin|nama_admin|no_hp_admin|pass_admin|Email_admin|
|---|---|---|---|---|
|1|asep kudt|087745671111|asepppus|@asepppgmail.com|
|2|alip Mandalika|087899881212|alippp|@alipsndahgmail.com|
|3|friday day|087899881212|afridayy|@friday.gmailcom|

#### Tabel pengguna
|🔑id_user|nama_user|Pass_user|email_user|
|---|---|---|---|
|1|asepp kaler|asepp12|@asepp.com|
|2|san day|sann13|@sanday.com|
|3|ujang|ujang14|@ujang.com|

#### Tabel Buku
|🔑id_buku|id_author|is_terbaik|is_terbaru|is_tamat|is_favorit|
|---|---|---|---|---|---|
|1|asepp kudet|sololev|overgear|naruto|zero|
|2|friday day|one peace|black clover|boruto|naruto|
|3|ujang|naruto|zero|war god|jaki|

#### Tabel author
|🔑id_author|nama_author|Nama_buku|
|---|---|---|
|1|rijal kaler|Overgear|
|2|tus day|kimetsu|
|2|tus day|war god|
|3|ruko|thunder god|

#### Tabel terbaik
|🔑is_terbaik|nama_buku|
|---|---|
|1|onepeace|
|2|zero|
|3|black clover|
##  Rancang solusi digital dari satu permasalahan yang ada di sekitar Anda
Aplikasi Baca Buku online (komil&Novel)
![pertemuan5-erd drawio (7)](https://user-images.githubusercontent.com/100669802/164587671-fa60d154-0342-4569-8143-1db65321fb81.png)
## posgresql
![WhatsApp Image 2022-04-22 at 8 39 48 AM](https://user-images.githubusercontent.com/100669802/164579862-e02506d1-79a2-441a-b4e6-4a829891d480.jpeg)
![WhatsApp Image 2022-04-22 at 8 45 59 AM](https://user-images.githubusercontent.com/100669802/164587027-e1d13f2e-67de-4c4e-9462-f7e2ec5e0742.jpeg)
![WhatsApp Image 2022-04-22 at 9 25 57 AM](https://user-images.githubusercontent.com/100669802/164587057-68e38186-da70-4174-8c92-2f7616667956.jpeg)
![WhatsApp Image 2022-04-22 at 10 15 24 AM](https://user-images.githubusercontent.com/100669802/164589586-137a5d5b-b52f-4bc0-8725-dc4a36eb804c.jpeg)

