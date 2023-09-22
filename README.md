# Jarkom-Modul-1-D30-2023

## Group Member    :
| Nama                              | NRP        |
|-----------------------------------|------------|
|Abdullah Yasykur Bifadhlil Midror  |5025211035  |
|Muhammad Ahyun Irsyada             |5025211251  |

Berikut adalah demo untuk praktikum modul 1

## Nomor 1
User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.

#### Soal A
Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 

#### Soal B 
Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 

**Penyelesaian :**
- Yang pertama kali dilakukan adalah melakukan filtering untuk protokol yang digunakan, yaitu `ftp`.
- Perlu diketahui bahwa untuk proses mengunggah, klien akan mengirimkan perintah FTP berupa command `USER`,`PASS`,`STOR`.
- Sehingga kemudian dicari satu-persatu pada kolom info, paket FTP mana yang melakukan request salah satu perintah diatas.
- Sequence number (raw) dan acknowledge number (raw) dari paket tersebut dapat dilihat di info TCP pada packet detail window.

**Hasil**
| <p align="center"> FTP Request untuk mengunggah </p> |
| -------------------------------------------- |
| <img src="https://github.com/FadhlyABD/Jarkom-Modul-1-D30-2023/blob/main/Images/soal1a.jpg" width = "400"/> |


#### Soal C 
Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

#### Soal D 
Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

**Penyelesaian :**
- Untuk mencari response dari request sebelumnya, maka tinggal cari paket response yang paling dekat dibawahnya

**Hasil**
| <p align="center"> FTP Response untuk mengunggah </p> |
| -------------------------------------------- |
| <img src="https://github.com/FadhlyABD/Jarkom-Modul-1-D30-2023/blob/main/Images/soal1b.jpg" width = "400"/> |

**Kesulitan Nomor 1 :**
- Kesulitan mencari kolom info untuk perintah FTP mengunggah (`USER`, `PASS`, `STOR`) karena belum tahu cara untuk filtering info

## Nomor 2
## Nomor 3
## Nomor 4
## Nomor 5
## Nomor 6
## Nomor 7
## Nomor 8
## Nomor 9
## Nomor 10
