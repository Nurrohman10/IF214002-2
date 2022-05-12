# **_SQL languages_**

---

**DDL** adalah nama pendek dari Data Definition Language, yang berhubungan dengan skema dan deskripsi basis data, tentang bagaimana data harus berada dalam basis data.

**DML** adalah nama pendek dari Bahasa Manipulasi Data yang berhubungan dengan manipulasi data, dan termasuk pernyataan SQL yang paling umum seperti SELECT, INSERT, UPDATE, DELETE dll, dan digunakan untuk menyimpan, memodifikasi, mengambil, menghapus dan memperbarui data dalam database.

**DCL** adalah nama pendek dari Bahasa Kontrol Data yang mencakup perintah seperti GRANT, dan sebagian besar berkaitan dengan hak, izin, dan kontrol lain dari sistem basis data.

---

## Datatypes

**text types**

|Data Type|Description|
|---|---|
|CHAR(size)|Memegang string panjang tetap (dapat berisi huruf, angka, dan karakter khusus). Ukuran tetap ditentukan dalam tanda kurung. Dapat menyimpan hingga 255 karakter|
|VARCHAR(size)|Memegang string panjang variabel (dapat berisi huruf, angka, dan karakter khusus). Ukuran maksimum ditentukan dalam tanda kurung. Dapat menyimpan hingga 255 karakter. Catatan: Jika Anda memasukkan nilai yang lebih besar dari 255, itu akan dikonversi menjadi tipe TEXT|
|TINYTEXT|Memegang string dengan panjang maksimum 255 karakter|
|TEXT|Memegang string dengan panjang maksimum 65.535 karakter|
|BLOB|Untuk BLOB (Objek Besar Biner). Menampung hingga 65.535 byte data|
|MEDIUMTEXT|Memegang string dengan panjang maksimum 16.777.215 karakter|
|MEDIUMBLOB|Untuk BLOB (Objek Besar Biner). Menampung hingga 16.777.215 byte data|
|LONGTEXT|Memegang string dengan panjang maksimum 4.294.967.295 karakter|
|LONGBLOB|Untuk BLOB (Objek Besar Biner). Menampung hingga 4.294.967.295 byte data|
|ENUM(x,y,z,etc.)|Memungkinkan Anda memasukkan daftar nilai yang mungkin. Anda dapat membuat daftar hingga 65535 nilai dalam daftar ENUM. Jika nilai yang dimasukkan tidak ada dalam daftar, nilai kosong akan dimasukkan.Catatan: Nilai diurutkan dalam urutan yang Anda masukkan.Anda memasukkan nilai yang mungkin dalam format ini: ENUM('X','Y' ,'Z')|
|SET|Mirip dengan ENUM kecuali bahwa SET dapat berisi hingga 64 item daftar dan dapat menyimpan lebih dari satu pilihan|


