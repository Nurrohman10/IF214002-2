![pertemuan5-erd drawio (4)](https://user-images.githubusercontent.com/100669802/163505824-a6747949-7616-4ff8-bb66-80b7a0ddcc2f.png)


## Tabel Normalisasi 1 dan 2

#### Tabel Admin
|🔑id_admin|nama_admin|no_hp_admin|pass_admin|alamat_admin|Email_admin|
|---|---|---|---|---|---|
|1|asep kudt|087745671111|asepppus|sukaweing Kaler|@asepppgmail.com|
|2|alip Mandalika|087899881212|alippp|caringin Kidul|@alipsndahgmail.com|
|3|friday day|087899881212|afridayy|negla|@friday.gmailcom|

#### Tabel pengguna
|🔑id_user|nama_user|Pass_user|gender_user|email_user|
|---|---|---|---|---|
|1|asepp kaler|asepp12|perempuan|@asepp.com|
|2|san day|sann13|laki-laki|@sanday.com|
|3|ujang|ujang14|laki-laki|@ujang.com|

#### Tabel Buku
|🔑id_buku|id_author|id_terbaik|id_terbaru|id_tamat|id_favorit|
|---|---|---|---|---|---|
|1|asepp kudet|sololev|overgear|naruto|zodak|
|2|friday day|one peace|black clover|boruto|overlord|
|3|ujang|naruto|zero|war god|batman|

#### Tabel author
|🔑id_author|nama_author|Nama_buku|
|---|---|---|
|1|rijal kaler|Overgear|
|2|tus day|kimetsu|
|2|tus day|war god|
|3|ruko|thunder god|

#### Tabel terbaik
|🔑id_terbaik|nama_buku|jenis_buku|
|---|---|---|
|1|Solo leveling|manga|
|2|wars god|manhwa|
|3|one peace|manhua|

#### Tabel terbaru
|🔑id_terbaru|nama_buku|jenis_buku|
|---|---|---|
|1|overgear|manga|
|2|black clover|manhwa|
|3|zero|manhua|

#### Tabel tamat
|🔑id_tamat|nama_buku|jenis_buku|
|---|---|---|
|1|boruto|manga|
|2|naruto|manhwa|
|3|martial peak|manhua|

#### Tabel favorit
|🔑id_favorit|nama_buku|jenis_buku|
|---|---|---|
|1|Solo leveling|manga|
|2|wars god|manhwa|
|3|one peace|manhua|

#### Tabel library
|🔑id_library|🔑id_favorit|riwayat_baca|
|---|---|---|
|1|1|csolo lev|
|2|2|zero|
|3|3|boruto|
