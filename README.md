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

   - **SIDOARJO**
   
    ![SIDOARJO](https://user-images.githubusercontent.com/49342639/101966298-d3492f00-3c49-11eb-868a-0ad9ec0abff8.PNG)

   - **PROBOLINGGO**
   
    ![PROBOLINGGO-1](https://user-images.githubusercontent.com/49342639/101966523-ab0e0000-3c4a-11eb-91c1-37b1be81bfeb.PNG)
    ![PROBOLINGGO-2](https://user-images.githubusercontent.com/49342639/101966524-aba69680-3c4a-11eb-8b01-68ec96d806b5.PNG)

   - **BANYUWANGI**
   
    ![BANYUWANGI](https://user-images.githubusercontent.com/49342639/101966606-f32d2280-3c4a-11eb-8133-79bdcad162f9.PNG)

   - **JEMBER**
   
    ![JEMBER](https://user-images.githubusercontent.com/49342639/101966697-4c955180-3c4b-11eb-8512-1c764657c207.PNG)

   - **BONDOWOSO**
   
    ![BONDOWOSO](https://user-images.githubusercontent.com/49342639/101966810-cdece400-3c4b-11eb-8804-358d02d180f9.PNG)

   - **BATU**
   
    ![BATU-1](https://user-images.githubusercontent.com/49342639/101966941-481d6880-3c4c-11eb-94c3-3972c008a180.PNG)
    ![BATU-2](https://user-images.githubusercontent.com/49342639/101966954-54a1c100-3c4c-11eb-8add-83f52ba32a31.PNG)
    ![BATU-3](https://user-images.githubusercontent.com/49342639/101966958-566b8480-3c4c-11eb-90fa-3638d4a3f68f.PNG)
   
   - **JOMBANG**
   
    ![JOMBANG](https://user-images.githubusercontent.com/49342639/101967040-b8c48500-3c4c-11eb-9aab-534f7fa1c821.PNG)
    
    - **MADIUN**
    
    ![MADIUN](https://user-images.githubusercontent.com/49342639/101967993-93854600-3c4f-11eb-9193-026f0aba28f9.PNG)

   - **BOJONEGORO**
   
    ![BOJONEGORO](https://user-images.githubusercontent.com/49342639/101968029-c0395d80-3c4f-11eb-8b3c-24313d895d84.PNG)

   - **NGANJUK**
   
    ![NGANJUK](https://user-images.githubusercontent.com/49342639/101968111-07275300-3c50-11eb-9b91-ae3f1b0a0b18.PNG)
    
    - **KEDIRI**
    
     ![KEDIRI-1](https://user-images.githubusercontent.com/49342639/101968220-9b91b580-3c50-11eb-9a29-2e4b12b8914b.PNG)
     ![KEDIRI-2](https://user-images.githubusercontent.com/49342639/101968223-9df40f80-3c50-11eb-80a1-6e310b1f3239.PNG)

    - **MALANG**
    
     ![MALANG](https://user-images.githubusercontent.com/49342639/101968252-bfed9200-3c50-11eb-8272-f174ea80983c.PNG)
     
     - **LUMAJANG**
     
     ![LUMAJANG](https://user-images.githubusercontent.com/49342639/101968364-6b96e200-3c51-11eb-865e-d4e804102916.PNG)

    - **BLITAR**
    
     ![BLITAR](https://user-images.githubusercontent.com/49342639/101968375-7baec180-3c51-11eb-8bcb-3d44adb58dbe.PNG)

    - **TULUNGAGUNG**
    
     ![TULUNGAGUNG](https://user-images.githubusercontent.com/49342639/101968391-8bc6a100-3c51-11eb-91b4-fcc4445043ca.PNG)
     
5. Routing pada setiap router dengan menambahkan dua perintah:
   1) ```post-up route add -net <NID> netmask <NETMASK> gw <GATEWAY>``` bertujuan agar  setelah *interfacenya* **nyala**, maka dia akan dapat secara otomatis menambahkan *static routenya*
   2) ```post-down route add -net <NID> netmask <NETMASK> gw <GATEWAY>``` bertujuan agar  setelah *interfacenya* **mati**, maka dia akan dapat secara otomatis menghilangkan *static routenya*
   
   Kedua perintah tersebut ditempatkan di file **/etc/network/interfaces/** dan di setiap barisan terbawah dari _interfaces_ yang menghubungkannya.
   
   
   - **SURABAYA**
  
    ![SURABAYA-2](https://user-images.githubusercontent.com/49342639/101968934-596a7300-3c54-11eb-89c8-283fb30ee0e1.PNG)
    ![SURABAYA-3](https://user-images.githubusercontent.com/49342639/101968937-5bcccd00-3c54-11eb-8e77-7f1fdcd7f83c.PNG)
    
    - **PASURUAN**
  
    ![PASURUAN-1](https://user-images.githubusercontent.com/49342639/101969143-6dfb3b00-3c55-11eb-85c0-aeec62ca5a28.PNG)
    ![PASURUAN-2](https://user-images.githubusercontent.com/49342639/101969146-70f62b80-3c55-11eb-8b48-c78895fb666c.PNG)
    
    - **PROBOLINGGO**
    
   ![PROBOLINGGO-1](https://user-images.githubusercontent.com/49342639/101976598-503fcd00-3c79-11eb-808b-7ef60bad2741.PNG)

   - **BATU**
    
    ![BATU-1](https://user-images.githubusercontent.com/49342639/101976735-bf69f100-3c7a-11eb-8fda-4a5f45c7d6c0.PNG)
    ![BATU-2](https://user-images.githubusercontent.com/49342639/101976737-c264e180-3c7a-11eb-99ed-3e259f1774a8.PNG)

   - **MADIUN**
   
    ![MADIUN](https://user-images.githubusercontent.com/49342639/101976751-e6282780-3c7a-11eb-83ee-7bfcf6e5d5e4.PNG)

   - **KEDIRI**
   
    ![KEDIRI-1](https://user-images.githubusercontent.com/49342639/101976756-f6400700-3c7a-11eb-9582-a9c4ef66be7d.PNG)
    ![KEDIRI-2](https://user-images.githubusercontent.com/49342639/101976757-f8a26100-3c7a-11eb-9890-8801e6deaf17.PNG)

   - **BLITAR**
   
    ![BLITAR](https://user-images.githubusercontent.com/49342639/101976761-07891380-3c7b-11eb-9d43-f7e4162cbb4a.PNG)




## Perhitungang CIDR
1. Dari proses penggabungan yang telah dilakukan, didapatkan sebuah subnet besar dengan netmask **/16**. Kali ini dapat menggunakan NID **192.168.0.0**, netmask **/16**
2. Menghitung pembagian IP dengan pohon berdasarkan penggabungan subnet yang telah dilakukan
   ![CIDR](https://user-images.githubusercontent.com/49342639/101978944-8be39280-3c8b-11eb-8cbf-f84d9cdc14f0.png)
   Sehingga, pembagian IP yang memungkinkan untuk topologi yang ada adalah sebagai berikut:
   | Subnet | NID             | Netmask |
   | :---:  | :---:           | :---:   |
   | A1     | 192.168.64.0    | /22     |
   | A2     | 192.168.192.0   | /30     |
   | A3     | 192.168.144.0   | /30     | 
   | A4     | 192.168.160.0   | /22     |  
   | A5     | 192.168.136.0   | /21     |  
   | A6     | 192.168.128.0   | /25     |  
   | A7     | 192.168.32.0    | /30     |  
   | A8     | 192.168.16.0    | /23     |  
   | A9     | 192.168.18.0    | /28     |  
   | A10    | 192.168.20.0    | /22     |  
   | A11    | 192.168.8.0     | /30     |  
   | A12    | 192.168.0.0     | /24     |  
   | A13    | 192.168.4.0     | /22     |
3. _Labelling IP_ sesuai pembagian IP yang didapatkan dari pohon **CIDR** pada setiap subnet yang telah terbagi pada tahap **Preface**
   ![Topologi](https://user-images.githubusercontent.com/49342639/101979222-d403b480-3c8d-11eb-92e1-6b4f53c81170.PNG)
4. Setting IP untuk masing-masing _interface_ yang ada di setiap _device_ sesuai dengan pembagian subnet pada pohon **CIDR**.
_Interface_ dapat diatur pada menu **Config > INTERFACE > “nama interface”**
   - **SURABAYA (Sebagai Router)**
     - IP pada Interface SURABAYA yang mengarah ke CLOUD
      
      ![Ke Cloud](https://user-images.githubusercontent.com/49342639/101979399-77a19480-3c8f-11eb-8d9f-8794df2e828f.PNG)

     - IP pada Interface SURABAYA yang mengarah ke MOJOKERTO
     
      ![Ke Mojokerto](https://user-images.githubusercontent.com/49342639/101979401-7a03ee80-3c8f-11eb-8bf4-d99866054d0a.PNG)

     - IP pada Interface SURABAYA yang mengarah ke PASURUAN
     
      ![Ke Pasuruan](https://user-images.githubusercontent.com/49342639/101979403-7b351b80-3c8f-11eb-9b9d-cc799b8f3b1e.PNG)

     - IP pada Interface SURABAYA yang mengarah ke SAMPANG
     
      ![Ke Sampang](https://user-images.githubusercontent.com/49342639/101979404-7c664880-3c8f-11eb-9602-6c11ac8caf9c.PNG)
  
     - IP pada Interface SURABAYA yang mengarah ke BATU
     
      ![Ke Batu](https://user-images.githubusercontent.com/49342639/101979405-7d977580-3c8f-11eb-9401-0bb08d190556.PNG)

   - **SAMPANG (Sebagai Klien)**
     - IP pada Interface SAMPANG yang mengarah ke SURABAYA
     
      ![Ke Surabaya](https://user-images.githubusercontent.com/49342639/101979568-a79d6780-3c90-11eb-8751-e8ba19339bf4.PNG)

   - **MOJOKERTO (Sebagai Server)**
     - IP pada Interface MOJOKERTO yang mengarah ke SURABAYA
     
      ![Ke Surabaya](https://user-images.githubusercontent.com/49342639/101983188-cc530880-3cab-11eb-9f1c-5abe1ad569e1.PNG)

   - **PASURUAN (Sebagai Router)**
     - IP pada Interface PASURUAN yang mengarah ke SURABAYA
     
      ![Ke Surabaya](https://user-images.githubusercontent.com/49342639/101983263-877ba180-3cac-11eb-876d-7fbcb55f28ad.PNG)

     - IP pada Interface PASURUAN yang mengarah ke PROBOLINGGO
     
      ![Ke Probolinggo](https://user-images.githubusercontent.com/49342639/101983361-38823c00-3cad-11eb-875a-c9bd7d70d9da.PNG)

     - IP pada Interface PASURUAN yang mengarah ke SIDOARJO
     
      ![Ke Sidoarjo](https://user-images.githubusercontent.com/49342639/101983381-5fd90900-3cad-11eb-8bf9-f83ce4c29981.PNG)

   - **PROBOLINGGO (Sebagai Router)**
     - IP pada Interface PROBOLINGGO yang mengarah ke PASURUAN
     
      ![Ke Pasuruan](https://user-images.githubusercontent.com/49342639/101983492-e261c880-3cad-11eb-9b3c-6c5aec71b107.PNG)
     - IP pada Interface PROBOLINGGO yang mengarah ke JEMBER dan BANYUWANGI
     
      ![Ke Jember   Banyuwangi](https://user-images.githubusercontent.com/49342639/101983496-e5f54f80-3cad-11eb-9399-be95b5f1946f.PNG)

     - IP pada Interface PROBOLINGGO yang mengarah ke BONDOWOSO
     
      ![Ke Bondowoso](https://user-images.githubusercontent.com/49342639/101983494-e4c42280-3cad-11eb-932a-55d326fb8f63.PNG)
      
   - **JEMBER (Sebagai Klien)**
     - IP pada Interface JEMBER yang mengarah ke PROBOLINGGO
     
      ![Ke Probolinggo](https://user-images.githubusercontent.com/49342639/101983705-594b9100-3caf-11eb-9188-266642843c38.PNG)

   - **BANYUWANGI (Sebagai Klien)**
     - IP pada Interface BANYUWANGI yang mengarah ke PROBOLINGGO
     
      ![Ke Probolinggo](https://user-images.githubusercontent.com/49342639/101983733-85671200-3caf-11eb-834a-55d970cd342d.PNG)

   - **BONDOWOSO (Sebagai Klien)**
     - IP pada Interface BONDOWOSO yang mengarah ke PROBOLINGGO
     
      ![Ke Probolinggo](https://user-images.githubusercontent.com/49342639/101983747-957ef180-3caf-11eb-8981-f5b84cede08b.PNG)
      
   - **BATU (Sebagai Router)**
     - IP pada Interface BATU yang mengarah ke SURABAYA
     
      ![Ke Surabaya](https://user-images.githubusercontent.com/49342639/101985108-80f32700-3cb8-11eb-854a-ee33d4e22852.PNG)

     - IP pada Interface BATU yang mengarah ke KEDIRI
     
      ![Ke Kediri](https://user-images.githubusercontent.com/49342639/101985118-95cfba80-3cb8-11eb-8dde-feb73c32783d.PNG)

     - IP pada Interface BATU yang mengarah ke JOMBANG dan MADIUN
     
      ![Ke Jombang dan Madiun](https://user-images.githubusercontent.com/49342639/101985193-18587a00-3cb9-11eb-9f67-1e1ef5c20430.PNG)

     - IP pada Interface BATU yang mengarah ke NGANJUK
     
      ![Ke Nganjuk](https://user-images.githubusercontent.com/49342639/101985205-28705980-3cb9-11eb-8dc6-f7f93053baec.PNG)

   - **JOMBANG (Sebagai Klien)**
     - IP pada Interface JOMBANG yang mengarah ke BATU dan MADIUN
     
      ![Ke Batu dan Madiun](https://user-images.githubusercontent.com/49342639/101985247-6bcac800-3cb9-11eb-8149-931d218a5311.PNG)

   - **MADIUN (Sebagai Router)**
     - IP pada Interface MADIUN yang mengarah ke BATU dan JOMBANG
     
      ![Ke Batu dan Jombang](https://user-images.githubusercontent.com/49342639/101985292-b4828100-3cb9-11eb-878f-e2133d6ed708.PNG)

     - IP pada Interface MADIUN yang mengarah ke BOJONEGORO
     
      ![Ke Bojonegoro](https://user-images.githubusercontent.com/49342639/101985320-ded43e80-3cb9-11eb-8f72-20ac4b0e03c3.PNG)

   - **BOJONEGORO (Sebagai Klien)**
     - IP pada Interface BOJONEGORO yang mengarah ke MADIUN
     
      ![Ke Madiun](https://user-images.githubusercontent.com/49342639/101985383-48544d00-3cba-11eb-8dc1-4ce598965b29.PNG)

   - **NGANJUK (Sebagai Klien)**
     - IP pada Interface NGANJUK yang mengarah ke BATU
     
      ![Ke Batu](https://user-images.githubusercontent.com/49342639/101985475-d3354780-3cba-11eb-9f11-fd778c2dd7a2.PNG)


   - **KEDIRI (Sebagai Router)**
     - IP pada Interface KEDIRI yang mengarah ke BATU
     
      ![Ke Batu](https://user-images.githubusercontent.com/49342639/101985535-39ba6580-3cbb-11eb-80d2-ffdbac2e7c48.PNG)

     - IP pada Interface KEDIRI yang mengarah ke MALANG
     
      ![Ke Malang](https://user-images.githubusercontent.com/49342639/101985546-48088180-3cbb-11eb-84a8-cbbc20704cfc.PNG)

     - IP pada Interface KEDIRI yang mengarah ke BLITAR dan LUMAJANG
     
      ![Ke Blitar dan Lumajang](https://user-images.githubusercontent.com/49342639/101985556-53f44380-3cbb-11eb-8240-2c623bb2a7bb.PNG)

   - **MALANG (Sebagai Server)**
     - IP pada Interface MALANG yang mengarah ke KEDIRI
     
      ![Ke Kediri](https://user-images.githubusercontent.com/49342639/101985588-97e74880-3cbb-11eb-9b21-f80b7fa3aede.PNG)

   - **BLITAR (Sebagai Router)**
     - IP pada Interface BLITAR yang mengarah ke KEDIRI dan LUMAJANG
     
      ![Ke Kediri dan Lumajang](https://user-images.githubusercontent.com/49342639/101985654-0a582880-3cbc-11eb-986f-2050059c1eb6.PNG)

     - IP pada Interface BLITAR yang mengarah ke TULUNGAGUNG
     
      ![Ke Tulungagung](https://user-images.githubusercontent.com/49342639/101985666-17751780-3cbc-11eb-9206-e9306dc655c6.PNG)

   - **LUMAJANG (Sebagai Klien)**
     - IP pada Interface LUMAJANG yang mengarah ke KEDIRI dan BLITAR
     
      ![Ke Kediri dan Blitar](https://user-images.githubusercontent.com/49342639/101985766-8fdbd880-3cbc-11eb-8209-c2d8d06af643.PNG)

   - **TULUNGAGUNG (Sebagai Klien)**
     - IP pada Interface TULUNGAGUNG yang mengarah ke BLITAR
     
      ![Ke Blitar](https://user-images.githubusercontent.com/49342639/101985805-c87bb200-3cbc-11eb-8ef8-1742e2ac38ab.PNG)
      
5. Routing pada setiap router. Routing dapat dilakukan pada menu **Config > Routing > Static** pada device Router. Lalu isi **Static Routes** dengan subnet tujuan yang ingin ditambahkan di dalam rute
   - **SURABAYA**
    ```
    192.168.27.148/30 via 192.168.27.146
    192.168.12.0/22 via 192.168.27.146
    192.168.0.0/21 via 192.168.27.146
    192.168.27.0/25 via 192.168.27.146
    192.168.24.0/23 via 192.168.27.154
    192.168.27.128 via 192.168.27.154
    192.168.16.0/22 via 192.168.27.154
    192.168.27.156/30 via 192.168.27.154
    10.151.73.156/30 via 192.168.27.154
    192.168.26.0/24 via 192.168.27.154
    192.168.20.0/22 via 192.168.27.154
    ```

   - **PASURUAN**
    ```
    0.0.0.0/0 via 192.168.27.145
    192.168.27.0/25 via 192.168.27.150
    192.168.0/21 via 192.168.27.150
    ```

   - **PROBOLINGGO**
    ```
    0.0.0.0/0 via 192.168.27.149
    ```

   - **BATU**
    ```
    0.0.0.0/0 via 192.168.27.153
    192.168.27.128/28 via 192.168.24.2
    10.151.73.156/30 via 192.168.27.158
    192.168.26.0/24 via 192.168.27.158
    192.168.20.0/22 via 192.168.27.158
    ```

   - **MADIUN**
    ```
    0.0.0.0/0 via 192.168.24.1
    ```

   - **KEDIRI**
    ```
    0.0.0.0/0 via 192.168.27.157
    192.168.20.0/22 via 192.168.26.2
    ```

   - **BLITAR**
    ```
    0.0.0.0/0 via 192.168.26.1
    ```
