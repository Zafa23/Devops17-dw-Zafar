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


