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
- Sequence number (raw) dan acknowledge number (raw) dari paket tersebut dapat dilihat di info TCP pada detail window.

**Jawaban :**
- Sequence number (raw) yang diperoleh bernilai `258040667` dan acknowledge number (raw) yang diperoleh bernilai `1044861039`

**Hasil**
| <p align="center"> FTP Request untuk mengunggah </p> |
| -------------------------------------------- |
| <img src="https://github.com/FadhlyABD/Jarkom-Modul-1-D30-2023/blob/main/Images/soal1a.jpg" width = "400"/> |


#### Soal C 
Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

#### Soal D 
Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?

**Penyelesaian :**
- Untuk mencari response dari request sebelumnya, maka tinggal cari paket response yang paling dekat dibawahnya.

**Jawaban :**
- Sequence number (raw) diperoleh bernilai `1044861039` dan acknowledge number (raw) diperoleh bernilai `258040696`

**Hasil**
| <p align="center"> FTP Response untuk mengunggah </p> |
| -------------------------------------------- |
| <img src="https://github.com/FadhlyABD/Jarkom-Modul-1-D30-2023/blob/main/Images/soal1b.jpg" width = "400"/> |

**Kesulitan Nomor 1 :**
- Kesulitan mencari kolom info untuk perintah FTP mengunggah (`USER`, `PASS`, `STOR`) karena belum tahu cara untuk filtering info

## Nomor 2

## Nomor 3
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:

#### Soal A 
Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?

#### Soal B 
Protokol layer transport apa yang digunakan?

**Penyelesaian :**
- Yang pertama kali dilakukan adalah melakukan filtering untuk memperoleh seluruh paket yang sesuai dengan yang diminta pada soal.
- Filter expression dengan `(ip.src == 239.255.255.250 && udp.srcport == 3702) || (ip.dst == 239.255.255.250 && udp.dstport == 3702)`.
- Setelah tampil seluruh paket yang sesuai, bisa dimulai untuk melakukan perhitungan secara manual jumlah paket yang tercapture.
- Protokol yang digunakan dapat dilihat baik di kolom protocol pada listing window maupun di keterangan pada detail window.

**Jawaban :**
- Jumlah paket yang tercapture setelah dilakukan perhitungan manual didapatkan `21 buah` dan protokol yang digunakan adalah `UDP`.

**Hasil**
| <p align="center"> Jumlah paket dan jenis protokolnya </p> |
| -------------------------------------------- |
| <img src="https://github.com/FadhlyABD/Jarkom-Modul-1-D30-2023/blob/main/Images/soal3.jpg" width = "400"/> |


## Nomor 4
Berapa nilai checksum yang didapat dari header pada paket nomor 130?

**Penyelesaian :**
- Yang pertama kali dilakukan hanyalah mencari paket nomor 130 pada listing window kemudian diklik untuk memperoleh info detailnya.

**Jawaban :**
- Nilai checksum dari paket tersebut dapat dilihat di dalam keterangan User Datagram Protocol pada detail window diperoleh `0x18e5`.

**Hasil**
| <p align="center"> Nilai checksum paket nomor 130 </p> |
| -------------------------------------------- |
| <img src="https://github.com/FadhlyABD/Jarkom-Modul-1-D30-2023/blob/main/Images/soal4.png" width = "400"/> |

## Nomor 5
## Nomor 6
## Nomor 7
## Nomor 8
## Nomor 9
## Nomor 10
