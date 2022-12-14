# Praktikum Jarkom Modul 1

Kelompok E05

Anggota:  
* Maula Izza Azizi - 5025201104
* Selfira Ayu Sheehan - 5025201174
* Brian Akbar Wicaksana - 5025201207

## Soal
**1. Sebutkan web server yang digunakan pada "monta.if.its.ac.id"!** 
```
http.host == monta.if.its.ac.id
```
<img width="680" alt="Screen Shot 2022-09-24 at 16 08 37" src="https://user-images.githubusercontent.com/72302421/192089964-c056dc7b-7829-4243-a867-5692098e6d82.png">

**2. Ishaq sedang bingung mencari topik ta untuk semester ini, lalu ia datang ke website monta dan menemukan detail topik pada website “monta.if.its.ac.id” , judul TA apa yang dibuka oleh ishaq?**  
<img width="682" alt="Screen Shot 2022-09-24 at 16 09 34" src="https://user-images.githubusercontent.com/72302421/192090028-96db7b25-d224-4d26-9d85-f66a866e2531.png">

<img width="682" alt="Screen Shot 2022-09-24 at 16 09 53" src="https://user-images.githubusercontent.com/72302421/192090046-7b646c5f-640f-45ea-b3b9-bc90780f535c.png">

**3. Filter sehingga wireshark hanya menampilkan paket yang menuju port 80!**  
    Untuk menampilkan paket yang menuju port 80, dapat menggunakan 
    ```
    tcp.dstport eq 80
    ```  
    Screenshot:  
    ![image](https://user-images.githubusercontent.com/80016547/192089256-788a83a4-b3d7-4f0e-8758-22ed072d7ce3.png)

    
**4. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 21!**  
    Untuk mengambil paket yang berasal port 21, dapat menggunakan 
    ```
    tcp.srcport eq 21
    ```  
    Screenshot:  
    ![image](https://user-images.githubusercontent.com/80016547/192089335-e12be13c-e09d-4695-9a88-939ec6f499df.png)

    
**5. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 443!**  
    Untuk mengambil paket yang berasal port 443, dapat menggunakan 
    ```
    tcp.srcport eq 443
    ```  
    Screenshot:  
    ![image](https://user-images.githubusercontent.com/80016547/192089430-fc16b68a-68a0-4285-b17c-03a109a83891.png)

        
**6. Filter sehingga wireshark hanya menampilkan paket yang menuju ke lipi.go.id!**  
   Pada CMD, ketik:  
   ```
   ping lipi.go.id
   ```
   Maka didapat:  
   ![image](https://user-images.githubusercontent.com/80016547/192089506-b07ded8e-0d49-45a1-ae25-68b21ca094dd.png)
   Diketahui bahwa id lipi.go.id adalah 203.160.128.158. Maka lakukan display filter:
   ```
   ip.dst eq 203.160.128.158
   ```
   Screenshot:  
   ![image](https://user-images.githubusercontent.com/80016547/192089585-1b1df254-9bdd-4c38-8e81-9b7702bd142b.png)

   
**7. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!**  
```     
ip.src == 192.168.100.173    
```

![No 7](https://user-images.githubusercontent.com/94432967/192090639-585e698a-6171-4fec-b662-c848d6919ee5.png)
    

**Untuk soal 8-10, silahkan baca cerita di bawah ini!**

**Di sebuah planet bernama Viltrumite, terdapat Kementerian Komunikasi dan Informatika yang baru saja menetapkan kebijakan baru. Dalam kebijakan baru tersebut, pemerintah dapat mengakses data pribadi masyarakat secara bebas jika memang dibutuhkan, baik dengan maupun tanpa persetujuan pihak yang bersangkutan. Sebagai mahasiswa yang sedang melaksanakan program magang di kementerian tersebut, kalian mendapat tugas berupa penyadapan percakapan mahasiswa yang diduga melakukan tindak kecurangan dalam kegiatan Praktikum Komunikasi Data dan Jaringan Komputer 2022. Selain itu, terdapat sebuah password rahasia (flag) yang diduga merupakan milik sebuah organisasi bawah tanah yang selama ini tidak sejalan dengan pemerintahan Planet Viltrumite. Tunggu apa lagi, segera kerjakan tugas magang tersebut agar kalian bisa mendapatkan pujian serta kenaikan jabatan di kementerian tersebut!**  

**8. Telusuri aliran paket dalam file .pcap yang diberikan, cari informasi berguna berupa percakapan antara dua mahasiswa terkait tindakan kecurangan pada kegiatan praktikum. Percakapan tersebut dilaporkan menggunakan protokol jaringan dengan tingkat keandalan yang tinggi dalam pertukaran datanya sehingga kalian perlu menerapkan filter dengan protokol yang tersebut.**  
Percakapan dilakukan oleh mahasiswa dengan ip address '127.0.0.1' dan '127.0.1.1'. Namun, saat difilter menggunakan
```
ip.src == 127.0.0.1 or ip.src == 127.0.1.1
```
tidak semua barisnya berisi percakapan. Untuk memfilter hanya percakapannya saja dapat menggunakan
```
tcp.flags.push == 1
```
Screenshot:
![No 8](https://user-images.githubusercontent.com/94432967/192090768-33b21f22-06a6-4c42-bb1a-5035d0805f7d.png)


**9. Terdapat laporan adanya pertukaran file yang dilakukan oleh kedua mahasiswa dalam percakapan yang diperoleh, carilah file yang dimaksud! Untuk memudahkan laporan kepada atasan, beri nama file yang ditemukan dengan format [nama_kelompok].des3 dan simpan output file dengan nama “flag.txt”.**  
Pertama, dilakukan pencarian paket yang berasal dari port 9002, seperti yang tertera pada percakapan no. 8, dengan ``tcp.srcport eq 9002``  
![image](https://user-images.githubusercontent.com/80016547/192101211-4c8bbec6-146e-450d-a9bb-407bc439c855.png)  
Kemudian, didapatkan paket yang memuat file salt. Paket tersebut kemudian di-follow melalui stream protokol TCP, sehingga didapatkan  
![image](https://user-images.githubusercontent.com/80016547/192101343-8cd2fe27-a3df-49e4-8fed-a8868562af3d.png)
Hasil stream kemudian di-save dalam bentuk raw dengan nama E05, format des3. Setelah itu bukalah gitbash dan jalankan command ```openssl des3 -d -salt -in E05.des3 -out flag.txt -k nakano```  
![image](https://user-images.githubusercontent.com/80016547/192101434-9af8c6c3-802f-4302-9703-15f26ebdc47c.png)  
Apabila file flag.txt dibuka, maka akan terlihat:  
![image](https://user-images.githubusercontent.com/80016547/192101476-a3f533f4-52c0-4f27-a9fd-4d9e6caf26c1.png)


**10. Temukan password rahasia (flag) dari organisasi bawah tanah yang disebutkan di atas!**  
Isi dari file flag.txt, seperti yang tertera di atas, adalah ```JaRkOm2022{8uK4N_CtF_k0k_h3h3h3}```.  
![image](https://user-images.githubusercontent.com/80016547/192104691-4f0f1743-1f0c-4814-83e3-ff717ed1e659.png)  

Sedangkan untuk password yang digunakan untuk membuka file des3, berdasarkan percakapan yang ditemukan pada nomer 8, ditemukan hint bahwa:  
```...passwordnya itu pake nama karakter anime yang kembar lima itu lho, jangan lupa pake huruf kecil semua```  
Melalui pencarian Google, didapatkan bahwa kembar lima tersebut memiliki nama belakang "Nakano", sehingga dapat disimpulkan bahwa password adalah nakano.
![image](https://user-images.githubusercontent.com/80016547/192101115-45ac3695-758b-47f5-8f22-54b3977da067.png)

## Kendala

- Pada saat praktikum, mengalami masalah saat decrypt file
