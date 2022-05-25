## Data Definition Language (DDL)
#### Create Table
#### Admin

```python
CREATE TABLE admin (
  id_admin INT NOT NULL PRIMARY KEY,
	nama_admin VARCHAR(50) NOT NULL,
	gender VARCHAR(50) NOT NULL,
	tanggal_lahir DATE NOT NULL,
	pass_admin VARCHAR (30) NOT NULL,
	email_admin VARCHAR (50) NOT NULL
);
```
#### User

```python
CREATE TABLE user (
  id_user INT NOT NULL PRIMARY KEY,
	nama_user VARCHAR(50) NOT NULL,
	gender VARCHAR(50) NOT NULL,
	tanggal_lahir DATE NOT NULL,
	pass_user VARCHAR (30) NOT NULL,
  history DATETIME NULL ,
  favorit DATETIME NULL ,
	email_user VARCHAR (50) NOT NULL
);
```
#### Buku

```python
CREATE TABLE buku (
  id_buku INT NOT NULL PRIMARY KEY,
  nama_buku VARCHAR (50) NOT NULL,
  tamat BOOLEAN NULL,
  terbaik BOOLEAN NULL,
  terbaru BOOLEAN NULL,
  id_author INT NOT NULL
);
```
#### Olah Data
```python
CREATE TABLE olahdata(
  id_admin INT NOT NULL,
  id_buku INT NOT NULL,
  data_buku DATETIMe NULL
  );
  ```
  
 #### Baca
 ```python
  CREATE TABLE baca(
  id_user INT NOT NULL PRIMARY KEY,
  id_buku Int NOT NULL,
  history DATETIME NULL,
  favorit DATETIME NULL
  );
```
#### author

```python
  CREATE TABLE author(
  id_author INt NOT NULL PRIMARY KEY,
  nama_author VARCHAR (50) NOT NULL
  );
  ```
 #### Alter Table
 ```python
 ALTER TABLE buku ADD COLUMN ( tipe SMALLINT)
 ```
  
### Data Manipulation Language (DML)
#### Insert Data
#### Admin
```python
INSERT INTO admin ( id_admin, nama_admin, gender, tanggal_lahir, pass_admin, email_admin) VALUES (1, 'ujang aep' , 'F', '1997-04-25', 'aepjang12', 'ujangaep@gmail.com');
INSERT INTO admin ( id_admin, nama_admin, gender, tanggal_lahir, pass_admin, email_admin) VALUES (1, 'uzumaki aep' , 'M', '1990-04-25', 'aepuzumaki12', 'uzumakiaep@gmail.com');
INSERT INTO admin ( id_admin, nama_admin, gender, tanggal_lahir, pass_admin, email_admin) VALUES (3, 'gusujang ' , 'F', '1996-09-25', 'gusujang12', 'gusujangaep@gmail.com');
INSERT INTO admin ( id_admin, nama_admin, gender, tanggal_lahir, pass_admin, email_admin) VALUES (4, 'sasuke' , 'M', '1993-01-05', 'sasuke12', 'sasukeaep@gmail.com');
```

#### User
```python
INSERT INTO user ( id_user, nama_user, gender, tanggal_lahir, pass_user, email_user, history, favorit) VALUES (1, 'sujang aep' , 'F', '1987-04-25', 'sepajang12', 'sujangsaep@gmail.com', '2022-01-02', '2022-02-04');
INSERT INTO user ( id_user, nama_user, gender, tanggal_lahir, pass_user, email_user, history, favorit) VALUES (2, 'fajar' , 'F', '2001-04-25', 'ksnjde12', 'fajar@gmail.com', '2022-11-12', '2022-12-07');
INSERT INTO user ( id_user, nama_user, gender, tanggal_lahir, pass_user, email_user, history, favorit) VALUES (3, 'rijik' , 'M', '1989-04-15', 'xjdeg12', 'rijik@gmail.com', '2022-11-11', '2022-12-02');
```

#### Buku
```python
INSERT INTO buku (id_buku, nama_buku, tamat, terbaik, terbaru, id_author) VALUES (1, 'One peace', '0', '1', '1', 1);
INSERT INTO buku (id_buku, nama_buku, tamat, terbaik, terbaru, id_author) VALUES (2, 'black clover', '1', '1', '0', 2);
INSERT INTO buku (id_buku, nama_buku, tamat, terbaik, terbaru, id_author) VALUES (3, 'naruto', '1', '1', '0', 3);
INSERT INTO buku (id_buku, nama_buku, tamat, terbaik, terbaru, id_author) VALUES (4, 'last boss', '0', '0', '1', 4);
INSERT INTO buku (id_buku, nama_buku, tamat, terbaik, terbaru, id_author) VALUES (5, 'Great mage', '1', '1', '0', 2);
INSERT INTO buku (id_buku, nama_buku, tamat, terbaik, terbaru, id_author) VALUES (6, 'God thunder', '0', '0', '1', 4);
INSERT INTO buku (id_buku, nama_buku, tamat, terbaik, terbaru, id_author) VALUES (7, 'sollev', '1', '1', '0', 3);
```
#### Update

```python
UPDATE buku 
SET 
  nama_buku = 'black clover',
  terbaru = '1'
WHERE 
  id_buku = 2
  ```
### DQL (Data query language)
```python
SELECT 
id_author,
    COUNT(*) AS jumlah_buku,
    (
      /* Menjumlahkan tiap nilai 1 atau 0 dari tiap record */
      SUM(
        /* Untuk tiap record, kalau gendernya M hitung 1 selain itu 0 */
        CASE WHEN terbaru='1' THEN 1 ELSE 0 END
      )
    ) AS terbaru
FROM buku
GROUP BY id_author
```
