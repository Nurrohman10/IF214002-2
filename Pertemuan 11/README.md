## Data Definition Language (DDL)

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
    register character varying COLLATE pg_catalog."default",
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
    CONSTRAINT baca_pkey PRIMARY KEY (id_user, id_buku),
    CONSTRAINT id_buku FOREIGN KEY (id_buku)
        REFERENCES public.buku (id_buku) MATCH SIMPLE
        ON UPDATE NO ACTION
        ON DELETE NO ACTION
        NOT VALID,
    CONSTRAINT id_user FOREIGN KEY (id_user)
        REFERENCES public."user" (id_user) MATCH SIMPLE
        ON UPDATE NO ACTION
        ON DELETE NO ACTION
        NOT VALID
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
    id_user integer NOT NULL,
    CONSTRAINT buku_pkey PRIMARY KEY (id_buku),
    CONSTRAINT id_author FOREIGN KEY (id_author)
        REFERENCES public.author (id_author) MATCH SIMPLE
        ON UPDATE NO ACTION
        ON DELETE NO ACTION
        NOT VALID,
    CONSTRAINT id_user FOREIGN KEY (id_user)
        REFERENCES public."user" (id_user) MATCH SIMPLE
        ON UPDATE NO ACTION
        ON DELETE NO ACTION
        NOT VALID,
    CONSTRAINT terbaik FOREIGN KEY (terbaik)
        REFERENCES public.terbaik (terbaik) MATCH SIMPLE
        ON UPDATE NO ACTION
        ON DELETE NO ACTION
        NOT VALID
)

TABLESPACE pg_default;

CREATE TABLE IF NOT EXISTS public.olahdata
(
    id_admin integer NOT NULL,
    id_buku integer NOT NULL,
    data_buku date,
    CONSTRAINT olahdata_pkey PRIMARY KEY (id_admin, id_buku),
    CONSTRAINT id_admin FOREIGN KEY (id_admin)
        REFERENCES public.admin (id_admin) MATCH SIMPLE
        ON UPDATE NO ACTION
        ON DELETE NO ACTION
        NOT VALID,
    CONSTRAINT id_buku FOREIGN KEY (id_buku)
        REFERENCES public.buku (id_buku) MATCH SIMPLE
        ON UPDATE NO ACTION
        ON DELETE NO ACTION
        NOT VALID
)

TABLESPACE pg_default;

```
```python
CREATE TABLE IF NOT EXISTS public.author
(
    id_author integer NOT NULL,
    nama_author character varying COLLATE pg_catalog."default",
    CONSTRAINT author_pkey PRIMARY KEY (id_author)
)

TABLESPACE pg_default;

CREATE TABLE IF NOT EXISTS public.terbaik
(
    terbaik boolean NOT NULL,
    views_buku integer,
    CONSTRAINT terbaik_pkey PRIMARY KEY (terbaik)
)

TABLESPACE pg_default;
```

### DML (Data Manipulation language)
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
INSERT INTO buku (id_buku,nama_buku,tamat,terbaik,terbaru,id_author, id_user) VALUES ('1', 'one peace', 'f', 't', 'f', '1', '1');
iNSERT INTO buku (id_buku,nama_buku,tamat,terbaik,terbaru,id_author, id_user) VALUES ('2', 'black clover', 'f', 't', 'f', '1', '2'); 
iNSERT INTO buku (id_buku,nama_buku,tamat,terbaik,terbaru,id_author, id_user) VALUES ('3', 'god thunder', 't', 't', 'f', '2', '2');
iNSERT INTO buku (id_buku,nama_buku,tamat,terbaik,terbaru,id_author, id_user) VALUES ('4', 'bleach', 't', 'f', 't', '2', '3');
iNSERT INTO buku (id_buku,nama_buku,tamat,terbaik,terbaru,id_author, id_user) VALUES ('5', 'naruto', 'f', 't', 't', '3', '3'); 
INSERT INTO buku (id_buku,nama_buku,tamat,terbaik,terbaru,id_author,id_user) VALUES ('6', 'hero', 't', 't', 't', '1', '1'); 
```

### DQL (Data query language)
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

SELECT
	A.id_buku id_buku,
    A.nama_buku nama_buku,
	g.nama_user nama_user
FROM
	buku A
INNER JOIN "user" G
    ON a.id_user = a.id_buku
```
```python
select 
id_author,
COUNT(*) AS jumlah_buku
   
   


from buku
group by id_author
```
