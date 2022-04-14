
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

||buku|
|---|---|
|PK|ID|
||Nama_buku|

||Histori Baca|
|---|---|
||Chapter_buku|


```sql
CREATE TABLE
```
```python
print("Quiz Pertemuan 7")
print("Terakhir dibaca")
databaseproducts_ tbl(
   product_id INT NOT NULL AUTO_INCREMENT,
   product_name VARCHAR(100) NOT NULL,
   product_manufacturer VARCHAR(40) NOT NULL,
   submission_date DATE,
   PRIMARY KEY ( product_id )
);
