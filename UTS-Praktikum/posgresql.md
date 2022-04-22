```sql
CREATE TABLE
```
```python
CREATE TABLE public."Admin"
(
    id_admin integer NOT NULL,
    nama_admin character(30) COLLATE pg_catalog."default" NOT NULL,
    pass_admin character(16) COLLATE pg_catalog."default" NOT NULL,
    email_admin character varying(50) COLLATE pg_catalog."default" NOT NULL,
    nomor_hp_admin integer NOT NULL,
    CONSTRAINT "Admin_pkey" PRIMARY KEY (id_admin)
)
WITH (
    OIDS = FALSE
)
TABLESPACE pg_default;

CREATE TABLE public."Buku"
(
    id_buku integer NOT NULL,
    nama_buku character(30) COLLATE pg_catalog."default" NOT NULL,
    is_tamat boolean,
    is_terbaru boolean,
    is_terbaik boolean,
    is_favorit boolean,
    CONSTRAINT "Buku_pkey" PRIMARY KEY (id_buku)
)
WITH (
    OIDS = FALSE
)
TABLESPACE pg_default;

CREATE TABLE public."User"
(
    id_user integer NOT NULL,
    nama_user character(50) COLLATE pg_catalog."default" NOT NULL,
    email_user character varying(50) COLLATE pg_catalog."default" NOT NULL,
    pass_user character varying(30) COLLATE pg_catalog."default" NOT NULL,
    favorit boolean,
    history date,
    CONSTRAINT "User_pkey" PRIMARY KEY (id_user)
)
WITH (
    OIDS = FALSE
)
TABLESPACE pg_default;

CREATE TABLE public.author
(
    id_author integer NOT NULL,
    nama_author character(20) COLLATE pg_catalog."default" NOT NULL,
    CONSTRAINT author_pkey PRIMARY KEY (id_author)
)
WITH (
    OIDS = FALSE
)
TABLESPACE pg_default;


CREATE TABLE public.baca
(
    id_user integer NOT NULL,
    id_buku integer NOT NULL,
    history date,
    CONSTRAINT baca_pkey PRIMARY KEY (id_user, id_buku)
)
WITH (
    OIDS = FALSE
)
TABLESPACE pg_default;

CREATE TABLE public.olahdata
(
    id_admin integer NOT NULL,
    id_buku integer NOT NULL,
    buku date,
    CONSTRAINT olahdata_pkey PRIMARY KEY (id_admin)
)
WITH (
    OIDS = FALSE
)
TABLESPACE pg_default;
