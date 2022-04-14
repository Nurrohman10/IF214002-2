
# Pemodelan Data Historis

# Quiz
## Pemanfaatan data historis
contoh data historis terakhir dibaca di suatu aplikasi
## Tabel terakhir di baca

||buku|
|---|---|
|PK|ID|
||Nama_buku|
||Chapter_buku|

||Histori Baca|
|---|---|
|PK|Id_buku|
|PK|Tanggal_baca|
||Chapter_buku|


```sql
CREATE TABLE
```
```python
print("Quiz Pertemuan 7")
print("Terakhir dibaca")
databaseproducts_ tbl(
   id_buku INT NOT NULL AUTO_INCREMENT,
   Nama_buku VARCHAR(100) NOT NULL,
   product_manufacturer VARCHAR(40) NOT NULL,
   submission_date DATE,
   PRIMARY KEY ( product_id )
);
