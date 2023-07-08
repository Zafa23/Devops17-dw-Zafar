# Task Week-1
## Task A. Introduction To DevOps
1. Development dan Operation. Di mana kedua kata tersebut bermakna menggabungkan proses development/pengembangan dari sebuah sistem/aplikasi dengan operation/operasional. DevOps adalah sebuah prinsip developer untuk mengkoordinasikan antar tim yaitu tim development dengan tim operations dengan efektif dan efisien.

2. Continuous Integration merupakan layanan yang diberikan DevOps untuk melakukan build dan automation testing. Kegiatan ini dikerjakan dengan menggunakan tools berupa Source Code Repository (SCR) untuk menemukan error code dan fixed code.
***
## Task A. Instalansi Ubuntu

![New.png](../Screenshoot/instal-ubuntu/New.png)
>Siapkan virtual box nya, jika sudah kalian cukup tekan 'ctrl+n' atau klik 'new'

![Name-Machine.png](../Screenshoot/instal-ubuntu/Name-Machine.png)
>Dan disini kalian cukup atur saja nama dan posisi kalian menyimpan tempat machine nya dimana jika sudah next dan jangan lupa masukan file iso ubuntu 20.04.5

![Ram.png](../Screenshoot/instal-ubuntu/Ram.png)
>Pada menu ram dan procecor kalian atur yang kalian inginkan semakin besar akan semakin banyak penyimpanan nya 

![hdd.png](../Screenshoot/instal-ubuntu/hdd.png)
>Disini kalian cukup atur di 25gb saja agar tidak terlalu besar 

![bridge.png](../Screenshoot/instal-ubuntu/bridge.png)
>jika sudah semua di atur ram dan hdd kalian gabungkan tombol 'ctrl+s' untuk membuka menu setting dan atur di bagian network ubah dari 'nat' ke 'bridge adapter'

![bahasa.png](../Screenshoot/instal-ubuntu/bahasa.png)
>Jika sudah pengaturan network kali ini akan masuk ke installasi ubuntu, pilih bahasa english saja ketika ada eror kita bisa mengecek nya di google 

![ip-awal.png](../Screenshoot/instal-ubuntu/ip-awal.png)
>Pada menu ip disini pilih yang bagian enp0s3 lalu pilih manual, tapi sebelum mengatur ip kita harus liat cmd terlebih dahulu untuk melihat ip windows dan gateway nya agar kita bisa menggunakan internet di dalam nya nanti 

![cmd.png](../Screenshoot/instal-ubuntu/cmd.png)
>pada menu cmd bisa mengambil yang gateway nya saja dan ipv4 address 

![ip-sett.png](../Screenshoot/instal-ubuntu/ip-sett.png)
>dan pada menu ini kita hanya perlu mengatur subnet kita akan menggunakan ipaddres window namun angka terakhir kita ubah menjadi 0/24 dan di addres nya silakan dilebihkan sesuai kemauan untuk gateway bisa menggunakan ip gateway windows untuk dns bisa menggunakan dns google saja

![ip-fix.png](../Screenshoot/instal-ubuntu/ip-fix.png)
>jika sudah diatur save dan ini tampilan jika sudah diatur 

![partisi.png](../Screenshoot/instal-ubuntu/partisi.png)
>untuk partisi bisa diatur dan tidak karna setelah install kita bisa mempratisi di dalam ubuntu nya

![partisi-clear.png](../Screenshoot/instal-ubuntu/partisi-clear.png)
>jika sudah kita save saja dan countinue

![ssh.png](../Screenshoot/instal-ubuntu/ssh.png)
>Pada bagian ssh bisa di ceklis dan dilanjut saja 

![installer.png](../Screenshoot/instal-ubuntu/installer.png)
>untuk menu ini kita lewati saja karna nanti bisa kita instal di dalam 

![boot.png](../Screenshoot/instal-ubuntu/boot.png)
>dan disini akan menginstall yang sudah kita masukan sebelumnya jdi tinggal nunggu saja sesuai jaringan kalau cepat maka proses ini akan cepat tapi jika jaringan lagi buruk maka installasi nya akan memakan waktu, dan jika sudah muncul 'reboot now' silakan di pilih lalu akan memproses masuk ke ubuntu nya

![login.png](../Screenshoot/instal-ubuntu/login.png)
>saat ketika sudah selesai menginstall nya akan tampil seperti ini kita cukup masukan 'username' dan 'password' di bagian password tidak akan muncul huruf atau angka kalian cukup ketikan saja dan enter maka kalian akan masuk

![update.png](../Screenshoot/instal-ubuntu/update.png)
>jika sudah login disini kita akan mengupdate nya sebelum update kita akan masuk root menggunakan sintaks `sudo su`

![login-putty.png](../Screenshoot/instal-ubuntu/login-putty.png)
>kita akan menggunakan putty untuk login ssh disini cukup masukan ip dan port nya saja

![login-putty(2).png](../Screenshoot/instal-ubuntu/login-putty(2).png)
>jika sudah akan tampil login dan kita akan coba mengtest jaringan yang kita buat 

![ping-putty.png](../Screenshoot/instal-ubuntu/ping-putty.png)
>Disini kita akan mengetest jaringan apakah sudah berjalan sesuai apa tidak dengan sintaks `ping google.com` atau `ping 8.8.8.8`
