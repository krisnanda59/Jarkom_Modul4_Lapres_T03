# Lapres Modul 4 Jarkom 2020 - T03
**Oleh:**
- I Made Dindra Setyadharma (05311840000008)
- Rindi Kartika Sari (05311840000013)

## Penyelesaian - Subnetting dan Routing
   ![Soal Shift Modul 4 (1)](https://user-images.githubusercontent.com/49342639/101732621-13949a00-3af0-11eb-947e-a90e095bc56c.png)
Topologi tersebut dilakukan perhitungan pembagian subnet dengan menggunakan metode **Classless** yaitu:
1. **VLSM (Variable Length Subnet Masking)** di UML
2. **CIDR (Clasless Inter Domain Routing)** di Cisco Packet Tracer

## Preface
1. Melakukan pembagian subnet terhadap topologi yang ada
   ![Topologi](https://user-images.githubusercontent.com/49342639/101887854-fafbb100-3bcf-11eb-8090-fc288e9ae4d2.png)
   Dari hasil pembagian subnet, kita mendapatkan sejumlah **13 subnet** dan **2 subnet untuk server**.

## Perhitungang VLSM
1. Menentukan jumlah alamat IP yang dibutuhkan oleh tiap subnet dari 13 subnet yang ada *(2 subnet untuk server tidak diikutkan dalam penentuan jumlah alamat IP, karena Server dikhususkan untuk menggunakan IP DMZ dari T3)*

   | Subnet | Jumlah IP | Netmask |
   | :---:  | :---:     | :---:   |
   | A1     | 1001      | /22     |
   | A2     | 2         | /30     |
   | A3     | 2         | /30     | 
   | A4     | 701       | /22     |  
   | A5     | 2021      | /21     |  
   | A6     | 101       | /25     |  
   | A7     | 2         | /30     |  
   | A8     | 502       | /23     |  
   | A9     | 13        | /28     |  
   | A10    | 521       | /22     |  
   | A11    | 2         | /30     |  
   | A12    | 252       | /24     |  
   | A13    | 721       | /22     |   
   | **Total**   | **5841**    | **/19**     |   

   Jadi, kita dapat menggunakan netmask **/19** untuk memberikan pengalamatan IP pada 13 subnet

2. Subnet besar yang kami bentuk memiliki NID **192.168.0.0** dengan netmask **/19**. Lalu, kita mulai dengan perhitungan pembagian IP dengan bantuan pohon IP
   ![VLSM](https://user-images.githubusercontent.com/49342639/101891944-4b294200-3bd5-11eb-8c69-05e57d656fb6.png)
   Sehingga, pembagian IP yang memungkinkan untuk topologi yang ada adalah sebagai berikut:
   | Subnet | NID             | Netmask |
   | :---:  | :---:           | :---:   |
   | A1     | 192.168.8.0     | /22     |
   | A2     | 192.168.27.144  | /30     |
   | A3     | 192.168.27.148  | /30     | 
   | A4     | 192.168.12.0    | /22     |  
   | A5     | 192.168.0.0     | /21     |  
   | A6     | 192.168.27.0    | /25     |  
   | A7     | 192.168.27.152  | /30     |  
   | A8     | 192.168.24.0    | /23     |  
   | A9     | 192.168.27.128  | /28     |  
   | A10    | 192.168.16.0    | /22     |  
   | A11    | 192.168.27.156  | /30     |  
   | A12    | 192.168.26.0    | /24     |  
   | A13    | 192.168.20.0    | /22     |  
3. Pembuatan jumlah router, switch, klien, dan banyaknya eth di UML disesuaikan dengan topologi yang diminta.
   Sintaks pembuatan topologi di UML ini berada pada file **topologi.sh**
   ![01 Membuat Topologi](https://user-images.githubusercontent.com/49342639/101911098-7bcba480-3bf2-11eb-8501-1bf534a990dd.PNG)

   Selain itu, kami juga membuat sintaks untuk mempermudah penutupan UML di file **bye.sh**
   ![02  Tutup UML](https://user-images.githubusercontent.com/49342639/101911358-d49b3d00-3bf2-11eb-9563-1a66c60e3879.PNG)
 4. Setting IP untuk setiap UML pada file **/etc/network/interfaces** sesuai dengan pembagian IP pada setiap subnet
   - **SURABAYA**
  
    ![SURABAYA-1](https://user-images.githubusercontent.com/49342639/101965538-94b27500-3c47-11eb-96a1-2b8cf5606610.PNG)
    ![SURABAYA-2](https://user-images.githubusercontent.com/49342639/101965487-67fe5d80-3c47-11eb-9e59-e3a1ca39e214.PNG)
    ![SURABAYA-3](https://user-images.githubusercontent.com/49342639/101965324-da227280-3c46-11eb-9eee-29ac73bea13a.PNG)

   - **SAMPANG**
    
    ![SAMPANG](https://user-images.githubusercontent.com/49342639/101965606-e2c77880-3c47-11eb-8227-8a2457b890bc.PNG)

   - **MOJOKERTO**
    
    ![MOJOKERTO](https://user-images.githubusercontent.com/49342639/101965952-f7f0d700-3c48-11eb-8f24-4863d6b66a4b.PNG)

   - **PASURUAN**
    
    ![PASURUAN-2](https://user-images.githubusercontent.com/49342639/101966221-941ade00-3c49-11eb-8415-8b723cf847f4.PNG)
