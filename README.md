![image](https://github.com/FadhlyABD/Jarkom-Modul-1-D30-2023/assets/114343225/ba37bc1b-032d-4f6a-835e-56f760311c7b)# Jarkom-Modul-1-D30-2023

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
**Soal**

Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer

**Penyelesaian**
Pertama tama filter protocol HTTP di display filter 

| <p align="center"> FTP Request untuk mengunggah </p> |
| -------------------------------------------- |
| <img src="https://github.com/FadhlyABD/Jarkom-Modul-1-D30-2023/blob/main/Images/No 2 (1).png" width = "400"/> |

Lalu klik paket yang memiliki protocol HTTP 

| <p align="center"> FTP Request untuk mengunggah </p> |
| -------------------------------------------- |
| <img src="https://github.com/FadhlyABD/Jarkom-Modul-1-D30-2023/blob/main/Images/No 2 (2).png" width = "400"/> |

lalu kita klik ``Hypertext Transfer Protocol`` dan klik info protocol nya di situ ada server dari portal praktikum jarkom 

**Hasil**

| <p align="center"> FTP Request untuk mengunggah </p> |
| -------------------------------------------- |
| <img src="https://github.com/FadhlyABD/Jarkom-Modul-1-D30-2023/blob/main/Images/No 2 (3).png" width = "400"/> |

Web Server dari portal Jarkom adalah ``gunicorn``

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
**Soal**

Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
a. Berapa banyak packet yang berhasil di capture dari file pcap tersebut?
b. Port berapakah pada server yang digunakan untuk service SMTP?
c. Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?

**Penyelesaian**

Pertama tama buka dulu file txt yang di pasword di dalam zip yang ada di soal dengan cara memfilter protocol SMTP (foto)

lalu pilih salah satu paket yang memiliki protocol SMTP,lalu kita klik kanan dan tekan tombol follow, klik tcp stream  (foto)

setelah itu cari pasrword yang ada di TCP stream nya  (foto)

setelah ketemu pasword nya, pasword tersebut harus di decode dulu menjadi suatu code yang dapat membuka file txt yang ada di zip (foto) 

setelah file txt nya terbuka, alamat ncat nya akan keluar yaitu ``nc 10.21.78.111 11111`` (foto)

#### Penyelesaian Nomor 5 A

Untuk menentukan berapa banyak paket yang berhasil di capture dari bisa di lihat di wireshark bagian bawah kanan yang telah di filter protocol SMTP nya ( foto ) 

#### Penyelesaian Nomor 5 B 

Untuk nenemukan port yang ada di server untuk servide SMTP dengan cara memfilter protocol SMTP di display filter, lalu kita pilih salah satu paket yang protocol nya bertipe SMTP, lalu kita cek di ``Transmission Tranfer Protocol`` lalu kita cari ``Destination port`` nya (foto) 

#### Penyelesaian Nomor 5 C

Untuk Menemukan IP yang merupakan IP public dengan cara mengecek apakah no alamat IP awal nya itu 74 atau tidak, jadi jika Ip paketnya di dahului dengan angka 74 maka IP tersebut merupakan Ip public (foto)

**Hasil**

Hasil dari decode pasword file txt adalah ``5implePas5word``
(foto)

alamat Ncat dari soal no 5 adalah ``nc 10.21.78.111 11111``
(foto)

#### Hasil Nomor 5 A 

Banyak paket yang di capture adalah ``60``

#### Hasil Norom 5 B



Destination Port ``25``

#### Hasil 5 C


jumlah alamat Ip yang merupakan IP publik adalah ``74.53.140.153`` 


## Nomor 6
## Nomor 7
**soal**

Berapa jumlah packet yang menuju IP 184.87.193.88?

**Penyelesaian**

Pertama tama filter paket yang destinasinya adalah IP 184.87.193.88 dengan menggunakan query ``ip.dst == 184.87.193.88``. hasil dari filter tersebut adalah : 

Setelah itu kita hitung paket yang destinasi nya ke IP 184.87.193.88 yaitu : 6
**Hasil**

| <p align="center"> FTP Request untuk mengunggah </p> |
| -------------------------------------------- |
| <img src="https://github.com/FadhlyABD/Jarkom-Modul-1-D30-2023/blob/main/Images/No 7.png" width = "400"/> |

## Nomor 8
**Soal**

Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)

**Penyelesaian**

query filter wireshark hanya mengambil semua protokol paket yang menuju port 80! yaitu ``tcp.dstport == 80 || udp.dstport == 80`` yang mana ``tcp`` adalah protocol yang di cari, lalu ``dstport`` adalah destinasi port nya,lalu ``||`` menunjukkan arti atau , lalu ``UDP`` adalah protocol yang di cari 

Jadi ``tcp.dstport == 80 || udp.dstport == 80`` hanya mengambil semua paket yang menuju port 80.

**Hasil**
| <p align="center"> FTP Request untuk mengunggah </p> |
| -------------------------------------------- |
| <img src="https://github.com/FadhlyABD/Jarkom-Modul-1-D30-2023/blob/main/Images/no 8 (1).png" width = "400"/> |

## Nomor 9
**Soal**

Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34

**Penyelesaian**

Query untuk menyelesaikan  wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat adalah ``ip.src == 10.51.40.1 && ip.dst != 10.39.55.34`` yang mana ``ip.src`` berfungsi untuk mencari source IP ,sedangkan ``ip.dst`` berfungsi untuk mencari ip destination,lalu ``!=`` menunjukkan bhawa nilai dari tidak sama dengan.

Jadi query ``ip.src == 10.51.40.1 && ip.dst != 10.39.55.34`` berfungsi untuk mengfilter paket yang source nya dari ip 10.51.40.1 dan destinasi nya bukan IP 10.39.55.34

**Hasil**

| <p align="center"> FTP Request untuk mengunggah </p> |
| -------------------------------------------- |
| <img src="https://github.com/FadhlyABD/Jarkom-Modul-1-D30-2023/blob/main/Images/no 9.png" width = "400"/> |\

## Nomor 10

**Soal**
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet

**Penyelesaian**

Pertama tama filter protocol di display filter dengan ``TELNET`` 

| <p align="center"> FTP Request untuk mengunggah </p> |
| -------------------------------------------- |
| <img src="https://github.com/FadhlyABD/Jarkom-Modul-1-D30-2023/blob/main/Images/no 10 (1).png" width = "400"/> |\

Lalu kita pilih salah satu paket yang memiliki protocol telnet, lalu klik kanan dan klik follow lalu klik TCP stream

| <p align="center"> FTP Request untuk mengunggah </p> |
| -------------------------------------------- |
| <img src="https://github.com/FadhlyABD/Jarkom-Modul-1-D30-2023/blob/main/Images/no 10 (2).png" width = "400"/> |\

Setelah itu cari stream hingga menemukan jawaban nya 

| <p align="center"> FTP Request untuk mengunggah </p> |
| -------------------------------------------- |
| <img src="https://github.com/FadhlyABD/Jarkom-Modul-1-D30-2023/blob/main/Images/no 10 (3).png" width = "400"/> |\

**Hasil**

jawaban dari soal no 10 berada di stream 2 yaitu: ``dhafin:kesayangannyak0k0`` 

| <p align="center"> FTP Request untuk mengunggah </p> |
| -------------------------------------------- |
| <img src="https://github.com/FadhlyABD/Jarkom-Modul-1-D30-2023/blob/main/Images/no 10 (4).png" width = "400"/> |\

**Kendala** 
masih harus nyari TCP stream satu persatu 
