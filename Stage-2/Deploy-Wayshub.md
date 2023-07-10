# Task A. Deploy Wayshub Frontend & Backend
Buatlah vm dengan spesifikasi
```
   - Appserver : 1 CPU, 2 GB RAM
   - Gateway : 1 CPU, 1 GB RAM
    Storage : 30 GB
```

![Server.png](../Screenshoot/Idclound/Server.png)
> Dan disini kalian akan mengatur jenis iso yang akan kalian pakai  disini saya pakai ubuntu untuk version nya menggunakan 22.04 dan server indonesia 

![Spek.png](../Screenshoot/Idclound/Spek.png)
> Disini kalian akan mengatur sesuai spesifikasi yang di butuhkan 


![Ssh.png](../Screenshoot/Idclound/Ssh.png)
> Cek untuk mengetahui ssh jika blm silakan buat ssh-keygen di powershell windows atau cmd


![User.png](../Screenshoot/Idclound/User.png)
> Jika sudah semua silakan masukin username dan password dan jangan lupa masukan ssh dibagian ssh ya


![gitclone.png](../Screenshoot/Idclound/gitclone.png)
> Setelah sudah masukan git clone wayshub frontend nya dan backend nya


![nvm14.png](../Screenshoot/Idclound/nvm14.png)
> jika sudah di clone mari kita install nvm version 14 nya 


![npm-install.png](../Screenshoot/Idclound/npm-install.png)
> lanjut kita akan menginstall semua modul yang akan di butuhkan seperti gambar in 


![start.png](../Screenshoot/Idclound/start.png)
> jika sudah terinstall maka jalankan dengan npm start 


![hasil.png](../Screenshoot/Idclound/hasil.png)
![hslbe.png](../Screenshoot/sszafar/hslbe.jpg)
> lalu masukan ip public yang sudah dibuat otomatis oleh si idclounds nya dalam port 3000

***
## Konfigurasi Myql 
![sqlins.png](../Screenshoot/sszafar/sqlins.jpg)
> Pertama sebelum memasuki konfigurasi dan semua tentang mysql kita perlu instalasi terlebih dahulu dengan perintah `sudo apt install mysql-server`

![insql.png](../Screenshoot/sszafar/insql.jpg)
> Jika sudah terinstall buat masuk lah ke mysql root untuk pembuatan akun dan pemberian hak akses

![createuser.png](../Screenshoot/sszafar/createuser.jpg)
> Jalankan perintah ini untuk pembuatan user atau bisa di copy saja di bagian bawah ini dan berikan hak akses juga

``` 
CREATE USER 'zafar'@'localhost' IDENTIFIED WITH mysql_native_password BY 'zafar';
atau
CREATE USER 'zafar'@'%' IDENTIFIED BY 'zafar2501';
```
```
GRANT ALL PRIVILEGES ON *.* TO 'zafar'@'%' WITH GRANT OPTION;
```
![securesql.png](../Screenshoot/sszafar/securesql.jpg)
> Selanjutnya melakukan setup keamanan di `sudo mysql_secure_installation`
 
***

## PM2 Ecosystem


> silakan buat pm2 ecosystem di masing masing folder yang sudah di clone di sebelum nya `pm2 ecosystem simple`

![ecofe.png](../Screenshoot/sszafar/ecofe.jpg)

**Lalu edit script yang udah di buat dari sebelumnya yaitu ecosystem.config.js**
```
wayshub-frontend
name  : "frontend",
script: "npm start"
```

```
wayshub-backend
name  : "backend",
script: "npm start"
```

**Jika sudah di install pm2 dan sudah konfigurasi ecosystem silakan jalankan `pm2 start`**
![eco-fe](../Screenshoot/sszafar/eco-fe.jpg)

![eco-be](../Screenshoot/sszafar/eco-be.jpg)

![crosscekpm.png](../Screenshoot/sszafar/crosscekpm.jpg)
***
## Integrasi Frontend TO Backend
**Sekarang kita akan mengintegrasi kan si frontend ke backend edit file api.js yang beralokasikan di frontend `wayshub-frontend/src/config`**


![lok.png](../Screenshoot/sszafar/lok.png)


**lali masukan script yang sudah dibuat dibawah ini**
```
import axios from 'axios';

const API = axios.create({
    baseURL: "http://api.zafar.studentdumbways.my.id/api/v1"
});

const setAuthToken = (token) => {
    if(token){
        API.defaults.headers.common['Authorization'] = `Bearer ${token}`;
    } else {
        delete API.defaults.headers.common['Authorization'];
    }
}

export {
    API,
    setAuthToken
}
```
![confjsinteg.png](../Screenshoot/sszafar/confjsinteg.jpg)
***
## Integrasi Backend To Sql
**Selanjutnya edit pada file config.json di dalam `wayshub-backend/config`**


![integsql.png](../Screenshoot/sszafar/integsql.jpg)
![db-wayshubsql.jpg](../Screenshoot/sszafar/db-wayshubsql.jpg)

***
## Squelize
**Instal npm squelize di folder backend**

![cliins.jpg](../Screenshoot/sszafar/cliins.jpg)

**Selanjutnya buat database sql dengan melakukan sequelize create & migrate dengan perintah**

```
sequelize db:create
```

```
sequelize db:migrate
```

![db-create.jpg](../Screenshoot/sszafar/dbcreate.jpg)

**Kemudian cek pada sql apakah sudah terbuat database dan tables nya**

```
SHOW DATABASES;
```

```
USE db-wayshub;
```

```
SHOW TABLES;
```

![showdatabase.png](../Screenshoot/sszafar/showdatabase.png)

***

## Gateway Nginx
> Sekarang masuk ke vm gateway dan buat dns di cloundflare 2 untuk backend dan frontend nya contoh sebagai berikut

`zafar.stundentdumbways.my.id` **Untuk frontend**
`api.zafar.stundentdumbways.my.id` **Untuk backend**

![dns-zafar.jpg](../Screenshoot/sszafar/dns-zafar.jpg)

**lalu install nginx pada server gateway nya**

![nginsins.jpg](../Screenshoot/sszafar/nginsins.jpg)

>setelah itu bisa membuat folder atau langsung saja disini saya sudah langsung saja membuat konfigurasi di sites-enabled/ jika ingin membuat folder baru dan berisikan konfigurasi, setela simpan tambahkan di file nginx.conf

**buat 2 file configurasi untuk backend dan frontend**

![foldernginx.jpg](../Screenshoot/sszafar/foldernginx.jpg) 

**lalu edit file configurai nya sepperti dibawah ini**

>Untuk file frontend.conf


```
server { 
    server_name zafar.stundentdumbways.my.id; 
    
    location / { 
             proxy_pass http://103.174.114.223:3000;
    }
}
```

![rproxy.conf.jpg](../Screenshoot/sszafar/rporxy.conf.jpg)

>lalu buat satu lagi buat backend.conf 


```
server { 
    server_name api.zafar.stundentdumbways.my.id; 
    
    location / { 
             proxy_pass http://103.174.114.223:5000;
    }
}
```

![rproxybe.png](../Screenshoot/sszafar/rproxybe.png)

***
## Test buat akun dan masang foto profil
> Sekarang kita tes apakah sudah berhasil, untuk tes nya menggunakan chrome dengan sintaks `zafar.stundentdumbways.my.id`

![hasil.jpg](../Screenshoot/sszafar/hasil.jpg)
>Jika berhasil akan menampilkan seperti ini jika sudah berhasi buat aku saja dengan di sign up

![hasil-signup.jpg](../Screenshoot/sszafar/hasil-signup.jpg) 
>jika sudah mengisi semua nya lalu sign-up jika sudah lakukan login lagi

![hasil-sigin.jpg](../Screenshoot/sszafar/hasil-sigin.jpg)
>dan ini tampilan awalan saat sig in nya masih kosong dan tidak ada pa apa sekarang kita akan menambahkan foto profil 

![anya.png](../Screenshoot/sszafar/anya.jpg)


