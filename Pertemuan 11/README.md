### Data Definition Language (DDL)

```python
CREATE TABLE admin (
  id_admin INT NOT NULL PRIMARY KEY,
	nama_admin VARCHAR(50) NOT NULL,
	gender VARCHAR(50) NOT NULL,
	tanggal_lahir DATE NOT NULL,
	pass_admin VARCHAR (30) NOT NULL,
	email_admin VARCHAR (50) NOT NULL
);

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

CREATE TABLE buku (
  id_buku INT NOT NULL PRIMARY KEY,
  nama_buku VARCHAR (50) NOT NULL,
  tamat BOOLEAN NULL,
  terbaik BOOLEAN NULL,
  terbaru BOOLEAN NULL,
  id_author INT NOT NULL
);

CREATE TABLE olahdata(
  id_admin INT NOT NULL,
  id_buku INT NOT NULL,
  data_buku DATETIMe NULL
  );
  
  CREATE TABLE baca(
  id_user INT NOT NULL PRIMARY KEY,
  id_buku Int NOT NULL,
  history DATETIME NULL,
  favorit DATETIME NULL
  );
  
  CREATE TABLE author(
  id_author INt NOT NULL PRIMARY KEY,
  nama_author VARCHAR (50) NOT NULL
  );
  
  
### Data Manipulation Language (DML)
