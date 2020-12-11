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
   | A4     | 701       | /30     |  
   | A5     | 2021      | /30     |  
   | A6     | 101       | /30     |  
   | A7     | 2         | /30     |  
   | A8     | 502       | /30     |  
   | A9     | 13        | /30     |  
   | A10    | 521       | /30     |  
   | A11    | 2         | /30     |  
   | A12    | 252       | /30     |  
   | A13    | 721       | /30     |   
   | **Total**   | **5841**    | **/19**     |   
