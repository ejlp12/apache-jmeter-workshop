# Memulai Web Test sederhana

Kita akan memulai load test sebuah web site sederhana, supaya cepat kita tidak akan membuat Test Plan secara manual tetapi akan 
menggunakan Template.

1. Jalankan JMeter

2. Buat Test Plan dari Template

   Klik menu File > Templates... atau klik Templates icon:
   
   ![](https://cloud.githubusercontent.com/assets/3068071/15265255/fe5bcee0-19a9-11e6-977b-d3e16e26a494.png)
   
   ![](http://jmeter.apache.org/images/screenshots/template_menu.png)
   
   Pilih "Building a Web Test Plan" dari window Template, lalu klik tombol "Create"
   
   ![](https://cloud.githubusercontent.com/assets/3068071/15265265/44f2dbbe-19aa-11e6-9919-861c00c19aef.png)
   
3. Hasilnya anda akan melihat sebuah Test Plan project seperti ini:
   
   Ekspansikan elemen "JMeter Users" dengan mengklik icon "O-" atau icon tanda "+" di Icon Bar
   
   ![](https://cloud.githubusercontent.com/assets/3068071/15265283/87ee2acc-19aa-11e6-98f2-49dad4857887.png)
   
4. Eksplor masing-masing elemen yang ada tree view disebelah kiri.
   
   ![](https://cloud.githubusercontent.com/assets/3068071/15265277/684a3846-19aa-11e6-88f1-2e369506e678.png)
   
5. Klik "build-web-test-plan"
   
   ![](https://cloud.githubusercontent.com/assets/3068071/15265283/87ee2acc-19aa-11e6-98f2-49dad4857887.png)

6. Klik "JMeter Users"
   
   ![](https://cloud.githubusercontent.com/assets/3068071/15274900/1b4dd4dc-1ae8-11e6-8590-ab8917841bf1.png)

7. Klik "HTTP Request Default"
   
   ![](https://cloud.githubusercontent.com/assets/3068071/15265301/f74af8c8-19aa-11e6-9b1d-97a5898e2a5d.png)

8. Klik "Home Page"
   
   ![](https://cloud.githubusercontent.com/assets/3068071/15265307/1f27e75c-19ab-11e6-8239-7a84f55609e4.png)

9. Klik "Graph Result"
   
   ![](https://cloud.githubusercontent.com/assets/3068071/15265313/363acb26-19ab-11e6-8ee7-7cd1e2615520.png)

10. Tambahakan sebuah elemen baru dengan tipe Listener yaitu "View Result Tree" dengan cara...
    
    Klik kanan pada elemen "JMeter Users" lalu pada pop-up menu pilih Add > Listener > View Result Tree
    
    ![](https://cloud.githubusercontent.com/assets/3068071/15265319/75d4550e-19ab-11e6-971f-7fe959af9907.png)
   
    Jika ada warning yang memberitahukan untuk menyimpan project Test Plan, klik tombol [Yes]
    
    ![](https://cloud.githubusercontent.com/assets/3068071/15265325/9ba8134c-19ab-11e6-9c53-294282c2be4c.png)
   
11. Jalankan Test Plan
    
    Sebelum menjalankan Test Plan, anda sebaiknya berada pada tampilan elemen Listener, klik "View Result Tree"
    lalu klik tombol [Start] pada Icon Bar diatas, atau klik pada Menu Bar, Run > Start
    
    ![](https://cloud.githubusercontent.com/assets/3068071/15265322/8a499332-19ab-11e6-8260-f45bb052c83b.png)
    
    atau
    
    ![image](https://cloud.githubusercontent.com/assets/3068071/15277493/7fff926a-1b30-11e6-8465-ab964b45792d.png)
   
12. Lihat hasilnya
   
    ![](https://cloud.githubusercontent.com/assets/3068071/15265339/f573b26e-19ab-11e6-9a39-54c9db89a191.png)
   
    ![](https://cloud.githubusercontent.com/assets/3068071/15265339/f573b26e-19ab-11e6-9a39-54c9db89a191.png)
