
# Pemodelan Data Historis

# Quiz
## Pemanfaatan data historis
## Perubahan ERD untuk entitas yang memiliki data historis
contoh data historis terakhir dibaca di suatu aplikasi
## Tabel terakhir di baca

||Readers|
|---|---|
|PK|ID|
||Name_book|
||Chapter_book|
- karena chapter yang telah dibaca dapat berubah saat baca terakhir kali, maka data historis perlu disimpan
- dengan bentuk entitas seperti diatas, data histori chapter tidak dapat diketahui
- maka membuat data entitas untuk menyimpan data histori chapter

||Readers|
|---|---|
|PK|ID|
||Name_book|

||Histori Baca|
|---|---|
|PK|Id_Readers|
|PK|Tanggal_baca|
||Chapter_book|

Dengan relasi
|Readers|1:M|Chapter_book|
|---|---|---|

```sql
CREATE TABLE
```
```python
print("Quiz Pertemuan 7")
print("Terakhir dibaca")
databaseproducts_ tbl(
   id_book INT NOT NULL AUTO_INCREMENT,
   Name_book VARCHAR(100) NOT NULL,
   chapter_book VARCHAR(40) NOT NULL,
   submission_date DATE,
   PRIMARY KEY ( id_book )
);
