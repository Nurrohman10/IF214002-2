### DDL
```python
CREATE TABLE IF NOT EXISTS public."user"
(
    id_user integer NOT NULL,
    nama_user character varying(30) COLLATE pg_catalog."default" NOT NULL,
    gender_user character varying(15) COLLATE pg_catalog."default" NOT NULL,
    pass_user character varying(30) COLLATE pg_catalog."default" NOT NULL,
    email_user character varying(50) COLLATE pg_catalog."default" NOT NULL,
    history date,
    favorit date,
    CONSTRAINT user_pkey PRIMARY KEY (id_user)
)

TABLESPACE pg_default;

CREATE TABLE IF NOT EXISTS public.admin
(
    id_admin integer NOT NULL,
    nama_admin character varying(30) COLLATE pg_catalog."default" NOT NULL,
    gender_admin character varying(15) COLLATE pg_catalog."default" NOT NULL,
    pass_admin character varying(20) COLLATE pg_catalog."default" NOT NULL,
    email_admin character varying(50) COLLATE pg_catalog."default" NOT NULL,
    CONSTRAINT admin_pkey PRIMARY KEY (id_admin)
)

TABLESPACE pg_default;

CREATE TABLE IF NOT EXISTS public.baca
(
    id_user integer NOT NULL,
    id_buku integer NOT NULL,
    history date,
    favorit date,
    CONSTRAINT baca_pkey PRIMARY KEY (id_user, id_buku)
)

TABLESPACE pg_default;

CREATE TABLE IF NOT EXISTS public.buku
(
    id_buku integer NOT NULL,
    nama_buku character varying COLLATE pg_catalog."default",
    tamat boolean,
    terbaik boolean,
    terbaru boolean,
    id_author integer NOT NULL,
    CONSTRAINT buku_pkey PRIMARY KEY (id_buku)
)

TABLESPACE pg_default;

CREATE TABLE IF NOT EXISTS public.olahdata
(
    id_admin integer NOT NULL,
    id_buku integer NOT NULL,
    data_buku date,
    CONSTRAINT olahdata_pkey PRIMARY KEY (id_admin, id_buku)
)

TABLESPACE pg_default;

```

### DML
#### admin
```python
INSERT INTO ADMIN (id_admin,nama_admin,gender_admin,pass_admin,email_admin) VALUES ('1', 'umild', 'f','bsyw7', 'umild@gmail.com');
INSERT INTO ADMIN (id_admin,nama_admin,gender_admin,pass_admin,email_admin) VALUES ('2', 'jaki', 'f','bjn6yw7', 'jakisd@gmail.com');
```
#### user
```python
INSERT INTO "user" (id_user,nama_user,gender_user,pass_user,email_user,history,favorit) VALUES ('1','kholis','f','hbjha3','kholis@gmail.com','2001-01-03','2001-04-05'
);
INSERT INTO "user" (id_user,nama_user,gender_user,pass_user,email_user,history,favorit) VALUES ('2','rijik','f','hbvsha3','rijik@gmail.com','2002-01-03','2003-04-05'
);
INSERT INTO "user" (id_user,nama_user,gender_user,pass_user,email_user,history,favorit) VALUES ('3','jajang','m','hknjkea3','jajang@gmail.com','2009-03-03','2010-04-05'
);
```

#### buku
```python
INSERT INTO buku (id_buku,nama_buku,tamat,terbaik,terbaru,id_author) VALUES ('1', 'one peace', 'f', 't', 'f', '1');
iNSERT INTO buku (id_buku,nama_buku,tamat,terbaik,terbaru,id_author) VALUES ('2', 'black clover', 'f', 't', 'f', '1'); 
iNSERT INTO buku (id_buku,nama_buku,tamat,terbaik,terbaru,id_author) VALUES ('3', 'god thunder', 't', 't', 'f', '2');
iNSERT INTO buku (id_buku,nama_buku,tamat,terbaik,terbaru,id_author) VALUES ('4', 'bleach', 't', 'f', 't', '2');
iNSERT INTO buku (id_buku,nama_buku,tamat,terbaik,terbaru,id_author) VALUES ('5', 'naruto', 'f', 't', 't', '3'); 
```

### DQL
#### jumlah buku tamat
```python
SELECT 
id_author,

    COUNT(*) AS jumlah_buku, 
   
    (
      /* Menjumlahkan tiap nilai 1 atau 0 dari tiap record */
      SUM(
        /* Untuk tiap record, kalau gendernya M hitung 1 selain itu 0 */
        CASE WHEN tamat='t' THEN 1 ELSE 0 END
        
      )
    ) AS tamat
FROM buku
GROUP BY id_author
```
#### jumlah buku terbaik
```python
SELECT 
id_author,

    COUNT(*) AS jumlah_buku, 
   
    (
      /* Menjumlahkan tiap nilai 1 atau 0 dari tiap record */
      SUM(
        /* Untuk tiap record, kalau gendernya M hitung 1 selain itu 0 */
        CASE WHEN tamat='t' THEN 1 ELSE 0 END
        )
        
      ) as buku_tamat,
      (
      /* Menjumlahkan tiap nilai 1 atau 0 dari tiap record */
      SUM(
        /* Untuk tiap record, kalau gendernya M hitung 1 selain itu 0 */
        CASE WHEN terbaik='t' THEN 1 ELSE 0 END
        )
        
      ) as buku_terbaik

FROM buku
GROUP BY id_author
```
```python

select
  nama_user,
    gender_user,
    pass_user
FROM "user" 
INNER JOIN buku
ON buku.id_user = "user".id_user
ORDER by nama_user;
```
