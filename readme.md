-untuk pull images dari docker hub
docker  pull  <image>:<tag>
contoh : docker pull ubuntu:16.04

-untuk melihat images yang sudah di pull  :
commend : docker images


-untuk mejalank image yang sudah di pull 
*untuk running biasa :docker run  -it <image_id> /bin/bash
contoh : docker run  -it 93fd78260bd1  /bin/bash
*untuk  mount  volume/ atau membaca folder main os : docker run  -v  <lokasi dis ex: c,e,h>:<directory yang mau dimount>:<direcory container untuk hasil maount >  -it <image id> /bin/bash
contoh : docker run  -v  e:/:/data  -it 93fd78260bd1 /bin/bash
*untuk open port  : docker run -p 127.0.0.1:<port di main os>:<port di container >/tcp  -it  <image_id>  /bin/bash
contoh : docker run  -p  127.0.0.1:9000:9000/tcp -it 93fd78260bd1 /bin/bash
*open port dan mount volume : docker run -p 127.0.0.1:<port di main os>:<port di container >/tcp  -v  <lokasi dis ex: c,e,h>:<directory yang mau dimount>:<direcory container untuk hasil maount >  -it <image id> /bin/bash
contoh :docker run -p 127.0.0.1:9000:9000/tcp -v e:/:/data  -it  93fd78260bd1 /bin/bash 


-menlist  container yang sudah di buat :
*untuk semua container 
commend : docker ps -a 
* untuk container yang sedang berjalan 
commen : docker ps

-untuk mejalankan  container yang sudah di buat 
* commend  : docker start  <container_id>
 

-untuk masuk ke bash container 
*masuk bash container :  docker exec -it <container_id> bash 
contoh : docker exec  -it  93fd78260bd1 bash 

-untuk keluar dari bash 
commend : exit


-untuk yang ingin melakukan perubaahan port  atau dir yang mau dimount tatpi  container sudah banyak lib2, atau dipedensi2  yang lainya dapat melakukan hal di bawh 
* kita  juga dapa mengepush ke docker hub ke akun kita, untuk cara ini pastikan udah punya  akun docker hub
* login terlebih dahulu dengan cara 
commend : docker login --username <username_anda> --password <password_anda>
* kita lakukan tag ke repo kita 
commend :docker tag <tag_dari_images_yang_akan_di_push> <username_anda>/<nama_repo_yang-anda_inginkan>
*melakukan push ke repos anda 
commend : docker push <username-anda>/<nama_repo_anda>
*lihat di akun docker hub anda  pastikan image yang di push udah di sana 
*selanjutnya, dapat dilakukan seperti menggunakan git 
command: docker commit <container_id> <username_anda>/<nama_repo_yang_tadi_dibikin>:<pesan seperti :versi2>
*setelah dilakukan commit maka dapat melakukan push kembali ke repository 
command  : docker push <username-anda>/<nama_repo_anda>


 