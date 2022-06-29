# Tugas
1. Sebagai pemimpin organisasi / perusahaan, dari data hasil aplikasi yang sudah dibuat, tentukan masalah-masalah prioritas untuk dicari solusinya !
2. Tentukan struktur data dan bentuk visualisasinya ! Ada contoh visualisasinya (screenshot)
3. Buat query SQL untuk mendapatkan data no. 2 tersebut !

## Data Buku
### #Masalah

1. berapa banyak pengunjung dalam tiap hari/bulan/tahun.
2. berapa banyak buku status (tamat-terpopuler-terbaru). 
3. berapa banyak buku yang memiliki author yang sama.
---
## Struktur data dan bentuk visualisasi
### Tes webservice
![image](https://user-images.githubusercontent.com/100669802/175322444-caa960fb-3bbe-4499-b909-f0375ceb695c.png)

#### pengunjung buku
![image](https://user-images.githubusercontent.com/100669802/175284108-cd302917-e217-4edd-a65d-e0efca440c71.png)


### data buku

![image](https://user-images.githubusercontent.com/100669802/175284940-9bd96d06-9dbe-40a4-9b81-6fc0c4ca3194.png)

## Query SQL
```python
$result = pg_query($dbconn, "select id_author, 
COUNT(*) AS jumlah_buku from buku group by id_author order by id_author; ") 
or exit("Error with quering database");
```
