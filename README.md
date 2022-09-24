# Praktikum Jarkom Modul 1

Kelompok E05

Anggota:  
* Maula Izza Azizi - 5025201104
* Selfira Ayu Sheehan - 5025201174
* Brian Akbar Wicaksana - 5025201207

## Soal
1. **Sebutkan web server yang digunakan pada "monta.if.its.ac.id"!** 
2. **Ishaq sedang bingung mencari topik ta untuk semester ini, lalu ia datang ke website monta dan menemukan detail topik pada website “monta.if.its.ac.id” , judul TA apa yang dibuka oleh ishaq?**  
3. **Filter sehingga wireshark hanya menampilkan paket yang menuju port 80!**  
    Untuk menampilkan paket yang menuju port 80, dapat menggunakan:
    ```
    tcp.dstport eq 80
    ```
    Screenshot:  
    ![image](https://user-images.githubusercontent.com/80016547/192089256-788a83a4-b3d7-4f0e-8758-22ed072d7ce3.png)

    
4. **Filter sehingga wireshark hanya mengambil paket yang berasal dari port 21!**  
    Untuk mengambil paket yang berasal port 21, dapat menggunakan:
    ```
    tcp.srcport eq 21
    ```
    Screenshot:  
    ![image](https://user-images.githubusercontent.com/80016547/192089335-e12be13c-e09d-4695-9a88-939ec6f499df.png)

    
5. **Filter sehingga wireshark hanya mengambil paket yang berasal dari port 443!**  
    Untuk mengambil paket yang berasal port 443, dapat menggunakan:
    ```
    tcp.srcport eq 443
    ```
    Screenshot:  
    ![image](https://user-images.githubusercontent.com/80016547/192089430-fc16b68a-68a0-4285-b17c-03a109a83891.png)

        
6. **Filter sehingga wireshark hanya menampilkan paket yang menuju ke lipi.go.id!**  
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

   
7. **Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!**  

**Untuk soal 8-10, silahkan baca cerita di bawah ini!**

**Di sebuah planet bernama Viltrumite, terdapat Kementerian Komunikasi dan Informatika yang baru saja menetapkan kebijakan baru. Dalam kebijakan baru tersebut, pemerintah dapat mengakses data pribadi masyarakat secara bebas jika memang dibutuhkan, baik dengan maupun tanpa persetujuan pihak yang bersangkutan. Sebagai mahasiswa yang sedang melaksanakan program magang di kementerian tersebut, kalian mendapat tugas berupa penyadapan percakapan mahasiswa yang diduga melakukan tindak kecurangan dalam kegiatan Praktikum Komunikasi Data dan Jaringan Komputer 2022. Selain itu, terdapat sebuah password rahasia (flag) yang diduga merupakan milik sebuah organisasi bawah tanah yang selama ini tidak sejalan dengan pemerintahan Planet Viltrumite. Tunggu apa lagi, segera kerjakan tugas magang tersebut agar kalian bisa mendapatkan pujian serta kenaikan jabatan di kementerian tersebut!**  

8. **Telusuri aliran paket dalam file .pcap yang diberikan, cari informasi berguna berupa percakapan antara dua mahasiswa terkait tindakan kecurangan pada kegiatan praktikum. Percakapan tersebut dilaporkan menggunakan protokol jaringan dengan tingkat keandalan yang tinggi dalam pertukaran datanya sehingga kalian perlu menerapkan filter dengan protokol yang tersebut.**  
9. **Terdapat laporan adanya pertukaran file yang dilakukan oleh kedua mahasiswa dalam percakapan yang diperoleh, carilah file yang dimaksud! Untuk memudahkan laporan kepada atasan, beri nama file yang ditemukan dengan format [nama_kelompok].des3 dan simpan output file dengan nama “flag.txt”.**  
10. **Temukan password rahasia (flag) dari organisasi bawah tanah yang disebutkan di atas!**  

## Kendala
