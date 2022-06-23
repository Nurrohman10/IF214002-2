## Data Buku
### #Masalah

1. berapa banyak pengunjung dalam tiap hari/bulan/tahun.
2. berapa banyak buku status (tamat-terpopuler-terbaru). 
3. berapa banyak buku yang memiliki author yang sama.
---

### tes webservice
![image](https://user-images.githubusercontent.com/100669802/175016826-f06de73d-0d94-4b81-8a0e-2bb438773da8.png)

#### pengunjung buku
![image](https://user-images.githubusercontent.com/100669802/175284108-cd302917-e217-4edd-a65d-e0efca440c71.png)


### data buku
```python
$result = pg_query($dbconn, "select id_author, 
COUNT(*) AS jumlah_buku from buku group by id_author order by id_author; ") 
or exit("Error with quering database");
```

![image](https://user-images.githubusercontent.com/100669802/175284940-9bd96d06-9dbe-40a4-9b81-6fc0c4ca3194.png)

