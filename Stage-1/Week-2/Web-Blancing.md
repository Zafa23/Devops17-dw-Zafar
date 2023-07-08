## Web Serve & Load Blancing
Sebelum memulai siapkan semua nya seperti instal nginx,nodejs,pm2 dan aplikasi yang akan di deploy kalau sudah langsung kita praktekan 
***

![npm.png](../Screenshoot/web-serve/npm.png)
>Sesudah install atau clone dumbflix masuk dan `npm install` didalam nya Setelah npm instal berhasil, jalankan `npm build` agar membundle aplikasi nya

![serve.png](../Screenshoot/web-serve/serve.png)
>Setelah npm run build berhasil jalankan perintah `npm install -g serve`


![pm2.png](../Screenshoot/web-serve/pm2.png)
>Jika sudah kita akan mengetes di pm2 dan nantinya akan berjalan di port 8080 langsung start saja dengan perintah `pm2 serve build`

![hasil.png](../Screenshoot/web-serve/hasil.png)
>untuk mengaksesnya cukup dengan ip kita dan port 8080 


![etc.png](../Screenshoot/web-serve/etc.png)
>Sekarang kita akan mengatur nanti nya si aplikasi dumbflix sudah punya nama dan alamat nya dan ga perlu akses menggunakan ip dan port, masuk ke `cd etc/nginx` lalu lihat di dalam nya ada apa saja,dan buat satu folder untuk membuat configurasi dengan perintah `sudo mkdir dumbways` 


![ip.png](../Screenshoot/web-serve/ip.png)
>jika sudah masuk kedalam folder yang tadi di buat lalu bikin file configurasi `sudo nano proxy.conf` lalu masukan kode yang dibawah ini dan ganti server name sesuai kalian dan proxy pas nya ganti juga ip dan port 8080

```
server { 
    server_name domain.com; 
    
    location / { 
             proxy_pass http://127.0.0.1:3000;
    }
}
```


![dmbw.png](../Screenshoot/web-serve/dmbw.png)
>Jika sudah mengatur proxy dan sekarang mengatur agar folder dumbways nya ke baca, pergi ke `sudo nano /etc/nginx/nginx.conf` dan atur nama folder dan beri /* gunanya agar membaca semua file yang ada di dalamnya


![startnginx.png](../Screenshoot/web-serve/startnginx.png)
>dan kita cek apakah nginx berjalan atau tidak jika sudah kita akan atur hosts 


![hosts.png](../Screenshoot/web-serve/hosts.png)
>Pergi ke `sudo nano /etc/hosts` dan tambahkan alamat dan ip nya agarr bisa di akses di web chrome 


![hostwin.png](../Screenshoot/web-serve/hostwin.png)
>Sama seperti hosts di ubuntu sekarang atur di windows agar bisa kebuka di web chromen nya untuk mengaturnya kalian perlu run administrator notepad lalu `ctrl+o` dan cari folder etc dan ada file host 


![ipwin.png](../Screenshoot/web-serve/ipwin.png)
>jika sudah ketemu tambahkan ip dan alamat yang akan diakses lalu `ctrl+s` lalu close notepad


![hasil-2.png](../Screenshoot/web-serve/hasil-2.png)
>jika sudah semu akses web chrome dengan nama yang kalian atur sebelumnya karna disini saya menggunakan nama saya jadi saya akses 'dumbfli-zafar.xyz'. 
