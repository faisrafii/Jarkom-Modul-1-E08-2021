# Jarkom-Modul-1-E08-2021

**KELOMPOK E08**
1. Fais Rafii Akbar Hidiya (05111940000026)
2. Zahra Dyah Meilani (05111940000069)
3. Aji Rindra Fakhrezi Putra Faisal (05111940000205)

### 1. Sebutkan webserver yang digunakan pada "ichimarumaru.tech"! 
**Gunakan filter expression :** `http.host == ichimarumaru.tech`  di display filter
kemudian Follow TCP Stream kemudian kita liat pada tulisan **Server**

  **Hasil :**
  
  ![Hasil](https://github.com/faisrafii/Jarkom-Modul-1-E08-2021/blob/main/pictures/nomor%201.png?raw=true)
  
### 2. Temukan paket dari web-web yang menggunakan basic authentication method!
**Gunakan filter expression :** `**http.authorization contains Basic**` di display filter
Kemudian cari bagian authorization disitu terdapat methodnya

 **Hasil :**
 
 ![Hasil](https://github.com/faisrafii/Jarkom-Modul-1-E08-2021/blob/main/pictures/nomor%202.png?raw=true)
 
### 3. Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!

Gunakan filter expression : `http.host == "basic.ichimarumaru.tech"` 
kemudian pada bagian Authorization, spesifik di bagian credentials disitu terdapat username dan password untuk login ke web
**Hasil :**

 ![Hasil](https://github.com/faisrafii/Jarkom-Modul-1-E08-2021/blob/main/pictures/nomor%203.png?raw=true)
 
 Username: kuncimenujulautan
 
 Password: tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN
 
 **Tampilan Web setelah berhasil Login :**
 
![Hasil](https://github.com/faisrafii/Jarkom-Modul-1-E08-2021/blob/main/pictures/nomor%203b.png?raw=true)

Lalu kita jawab pertanyaan yang disediakan yaitu urutan pengkabelan T568A yaitu :

Urutan ke 1 : Putih Hijau TD+ (data kirim+)

Urutan ke 2 : Hijau TD- (data kirim-)

Urutan ke 3 : Putih Orange RD+ (data terima +)

Urutan ke 4 : Biru NC (tidak dipakai)

Urutan ke 5 : Putih Biru NC (tidak dipakai)

Urutan ke 6 : Orange RD- (data terima -)

Urutan ke 7 : Putih Coklat NC (tidak dipakai)

Urutan ke 8 : Coklat NC (tidak dipakai)

### 4. Temukan paket mysql yang mengandung perintah query select!

Gunakan wireshark filter expression : `mysql.query contains "select"`

**Hasil**

![Hasil](![image](https://user-images.githubusercontent.com/81347366/134761686-b0798950-5eba-4eeb-bdd1-6e412b2c0be4.png)

**Error/Kendala**

Harus ada case sensitive & insensitive, jadi seharusnya ada 3 query select 

**Penyelesaian Error**

Menggunakan filter expression `mysql contains SELECT || mysql contains select`

**Hasil**

![Hasil](https://user-images.githubusercontent.com/81347366/134761751-162cf904-b7ac-454b-98b2-c56543163a87.png)

Terlihat ada 3 perintah query select yang seharusnya muncul

### 5. Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!

Gunakan filter expression : `mysql.query contains "INSERT"`

### 6. Cari username dan password ketika melakukan login ke FTP Server!
### 7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")
### 8. Cari paket yang menunjukan pengambilan file dari FTP tersebut!
  Gunakan wireshark filter expression : ```ftp.request.command == RETR```
  
  **Dan Hasilnya tidak ada paket yang terambil:** 
  
  ![Hasil](https://github.com/faisrafii/Jarkom-Modul-1-E08-2021/blob/54351ca5097bcbcfd344cfcec269abc9abe222a3/pictures/nomor%208.png) 
  
### 9. Dari paket-paket yang menuju FTP terdapat inidkasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!
  Gunakan wireshark filter expression : ```ftp-data.command contains "secret.zip"``` untuk menangkap semua paket yang mengandung `secret.zip`
  
  **Hasil :**
  
  ![Hasil](https://github.com/faisrafii/Jarkom-Modul-1-E08-2021/blob/8677cf16c56ef234f8bec6a4c79a1e314a693797/pictures/nomor%209a.png)

  Setelah itu `follow tcp stream` salah satu packet dan set show and save data as `Raw` kemudian save file tersebut.
  
  ![Hasil](https://github.com/faisrafii/Jarkom-Modul-1-E08-2021/blob/8677cf16c56ef234f8bec6a4c79a1e314a693797/pictures/nomor%209b.png)

  **Hasil :**
  
  ![Hasil](https://github.com/faisrafii/Jarkom-Modul-1-E08-2021/blob/8677cf16c56ef234f8bec6a4c79a1e314a693797/pictures/nomor%209c.png)

### 10. Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!
  Gunakan wireshark filter expression : ```ftp-data.command contains "history.txt"``` untuk menangkap semua paket yang mengandung `history.txt`
  
  **Hasil :**
  
  ![Hasil](https://github.com/faisrafii/Jarkom-Modul-1-E08-2021/blob/4bacd715d978581dbb7c6d238f5b0d11886be65c/pictures/nomor%2010a.png)
  
  Setelah itu `follow tcp stream` paket tersebut untuk melihat history bash tersebut
  
  ![Hasil](https://github.com/faisrafii/Jarkom-Modul-1-E08-2021/blob/4bacd715d978581dbb7c6d238f5b0d11886be65c/pictures/nomor%2010b.png)
  
  Gunakan wireshark filter expression : ```ftp-data.command contains "bukanapaapa.txt"``` karena hint yang ditunjukkan adalah file `bukanapaapa.txt`.
  
  ![Hasil](https://github.com/faisrafii/Jarkom-Modul-1-E08-2021/blob/a12c3e1a826b6c5b345588c68f2b30789f588e6b/pictures/nomor%2010f.png)
  
  
  Setelah itu `follow tcp stream` paket tersebut dan didalamnya merupakan password dari file yang ada di dalam `secret.zip`
  
  ![Hasil](https://github.com/faisrafii/Jarkom-Modul-1-E08-2021/blob/a12c3e1a826b6c5b345588c68f2b30789f588e6b/pictures/nomor%2010c.png)
  
  Gunakan password tersebut untuk membuka file yang ada di `secret.zip`
  
  ![Hasil](https://github.com/faisrafii/Jarkom-Modul-1-E08-2021/blob/a12c3e1a826b6c5b345588c68f2b30789f588e6b/pictures/nomor%2010e.png)
  
  **Isi File :**
  
  ![Hasil](https://github.com/faisrafii/Jarkom-Modul-1-E08-2021/blob/a12c3e1a826b6c5b345588c68f2b30789f588e6b/pictures/nomor%2010d.png)
  
  
### 11. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80! 
### 12. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
### 13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
### 14. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!
### 15. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
