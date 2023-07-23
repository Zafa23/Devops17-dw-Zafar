# Monitoring 
sebelum mulai persiapkan hal hal dibawah ini terlebih dahulu yaitu:
- Install doker di monitoring
- Siapkan scrip promethus jib dan grafana (atau bisa dijadikan satu saja)
- Periksa apakah node-exporter sudah berjalan dan periksa di appserver dan gateway nya

![1.png](../_resources/1-2.png)
> Jika sudah kita akan masuk setingan scriptnya 


![2.png](../_resources/2-2.png)
> Buat script seperti ini atau bisa di coppy saja

```
scrape_configs:
- job_name: grafana   
  scrape_interval: 5s
  static_configs:
  - targets:
    - masukan IP:PORT 
    - masukan IP:PORT
```


![3.png](../_resources/3-2.png)
> Jika sudah kita langsung jalankan saja prometheus dan grafana nya seperti di gambar

```
docker run -d -p 9090:9090 -v ~/prometheus.yml:/etc/prometheus/prometheus.yml prom/prometheus
```
```
docker run -d -p 3000:3000 grafana/grafana
```


![4.png](../_resources/4-2.png)
> Jika sudah bisa di cek pakai ip:host atau jika sudah membuat dns domain di cloudflare bisa di coba juga jalankan di web browser


![5.png](../_resources/5-2.png)



![6.png](../_resources/6-2.png)
> disini saya akan memeriksa apakah sudah ada dns/ip server yang ditargetkan maka prometheus sudah terhubung dengan node-exporter

#Langkah Langkah Untuk Menambahkan Data Source
![7.png](../_resources/7-2.png)



![8.png](../_resources/8-1.png)



![9.png](../_resources/9-1.png)



![10.png](../_resources/10-1.png)


# Langkah Langkah Setup Dashboard
![11.png](../_resources/11-1.png)



![12.png](../_resources/12-1.png)


- CPU
```
100 - (avg by(instance) (irate(node_cpu_seconds_total{mode="idle", job="grafana"}[5m])) * 100)
```
![13.png](../_resources/13-1.png)

- Disk Usage
```
100 - (node_filesystem_avail_bytes / node_filesystem_size_bytes * 100)
```
![14.png](../_resources/14-1.png)

- Ram
```
100 * (1 - ((avg_over_time(node_memory_MemFree_bytes[10m]) + avg_over_time(node_memory_Cached_bytes[10m]) + avg_over_time(node_memory_Buffers_bytes[10m])) / avg_over_time(node_memory_MemTotal_bytes[10m])))
```
![15.png](../_resources/15-1.png)



## Save Dashboard
![16.png](../_resources/16.png)
> di pojok kanan akan ada seperti lambang save dan masukan nama save yang akan kita mau masukan


![17.png](../_resources/17.png)
> Sekarang kita akan coba menambahkan bot alert ke discord pilih menu allerting


![18.png](../_resources/18-1.png)
> bikin webhook terlebih dahulu lalu salin link webhook 


![19.png](../_resources/19.png)
> buat seperti diatas ini tambahkan discord atau jika yang lain ada pilihannya sesuaikan yang akan kalian pilih


![20.png](../_resources/20.png)
>Jika sudah kita akan coba test notification jika sudah maka akan muncul gambar yang dibawah ini


![21.png](../_resources/21.png)

