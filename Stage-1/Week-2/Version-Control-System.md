## Version Control System
1. version control adalah sebuah sistem yang merekam seluruh perubahan pada file atau set file dari waktu ke waktu 
***
## SSH KEYGEN

![ssh.png](../Screenshoot/control-system/ssh.png)
>Buka terminal di window terlebih dahulu bikin ```ssh-keygen```

![cat.png](../Screenshoot/control-system/cat.png)
>Jika sudah masukin kode kaya di gambar untuk melihat kode yang akan di tempel di ubuntu nya nantinya ketika kita login tidak perlu diminta pasword lagi untuk sintaks nya seperti ini ```cat .ssh/id_rsa.pub```

![aut.png](../Screenshoot/control-system/aut.png)
>jika sudah disalin kita akan pergi ke ubuntu dan masuk ke folder ssh dan menaruh kode yang dari windows di dalam authorized_keys untuk pergi ke foldernya kalian cukup masukan seperti ini ```sudo nano .ssh/authorized_keys``` 

![catubuntu.png](../Screenshoot/control-system/catubuntu.png)
>lalu kita akan melihat isi dari id_rsa.pub nya ubuntu jika blm ada file ini kalian cukup masukan ssh-keygen dan lewatin semuanya jika ada minta masukan y/n pilih y untuk sudah ada cara melihat nya adalah ```cat .ssh/id_rsa.pub```

![github.png](../Screenshoot/control-system/github.png)
>jika yang dari ubuntu sudah kalian salin pergi ke laman github dan pergi ke pengaturan pergi ke ssh dan add new ssh masukan kode yang ada di ubuntu 

![user.png](../Screenshoot/control-system/user.png)
>jika sudah kita akan mensetting terlebih dahulu untuk user name dan user mail kita agar kita tidak ditanya lagi saat push untuk sintaks kalian cukup ikutin urutan disebelah ini 


![file.png](../Screenshoot/control-system/file.png)
>lalu pergi ke folder yang ingin di taro di repo kita seblum itu kita persiapkan repo baru dulu harap membikin sesuai nama repo yang rapih dan bagus


![reset.png](../Screenshoot/control-system/reset.png)
>jika ada file yang ke ikut kalian cukup mereset dengan nama filenya saja agar tidak ke push


![push.png](../Screenshoot/control-system/push.png)
>jika sudah harap ikutin sesuai dari repo agar tidak ada eror 


![git.png](../Screenshoot/control-system/git.png)
>periksa jika sudah di push apakah sudah masuk


![menambahkan.png](../Screenshoot/control-system/menambahkan.png)
>Kali ini akan menambahkan 2 branch yaitu staging dan production untuk menambahkan kalian bisa double seperti kode yang di gambar agar bertujuan satu kali kerja saja 

![pro.png](../Screenshoot/control-system/pro.png)
>Dan disini kita akan ubah si file 1 akan berada di branch nya si production 


![staging.png](../Screenshoot/control-system/staging.png)
>untuk staging juga sama disini cukup menggunakan file4 saja dan kembali periksa apakah semua sudah ke push 

![branch.png](../Screenshoot/control-system/branch.png)

>disini untuk memeriksa semua branch yang pernah kita push sebelumnya di terminal
***
1.`git log` untuk melihat seluruh commit dan push dari jam berapa dan hari apa

2. `git reset` untuk membatalakan sebuah file atau folder yang gak sengaja ter input 

3. `git diff` membandingkan dan mengamati perbedaan antara dua branch, commit, dan juga dokumen 