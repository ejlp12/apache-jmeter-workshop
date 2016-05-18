
# Menjalankan JMeter dengan mode console (Tanpa GUI)


Save project sebelumnya dengan mengklik tombol save atau dari Menu Bar pilih File > Save

Berinama `build-web-test-plan.jmx` dan simpan di sebuah direktori misalnya `/tmp/jmeter` 

![image](https://cloud.githubusercontent.com/assets/3068071/15345134/ab242abc-1cd6-11e6-8c25-a3ded673275a.png)

Masuk ke direktori `<JMETER_HOME>/bin`

```
$ ./jmeter -n -t /tmp/jmeter/build-web-test-plan.jmx -l /tmp/jmeter/test-result.jtl
Creating summariser <summary>
Created the tree successfully using /tmp/jmeter/build-web-test-plan.jmx
Starting the test @ Wed May 18 09:05:53 WIB 2016 (1463537153243)
Waiting for possible shutdown message on port 4445
summary +     13 in     7s =    1.9/s Avg:  1549 Min:   225 Max:  3349 Err:     0 (0.00%) Active: 4 Started: 5 Finished: 1
summary +      7 in   3.1s =    2.3/s Avg:  1186 Min:   102 Max:  4133 Err:     0 (0.00%) Active: 0 Started: 5 Finished: 5
summary =     20 in    10s =    2.0/s Avg:  1422 Min:   102 Max:  4133 Err:     0 (0.00%)
Tidying up ...    @ Wed May 18 09:06:03 WIB 2016 (1463537163408)
... end of run
```

Berikut hasil test tersebut yaitu file `test-result.jtl` yang merupakan file CSV

```
$ cat /tmp/jmeter/test-result.jtl
1463537154470,1405,Home Page,200,OK,JMeter Users 1-2,text,true,10701,3,3,1007
1463537154194,1725,Home Page,200,OK,JMeter Users 1-1,text,true,10701,3,3,1288
1463537155465,963,Home Page,200,OK,JMeter Users 1-3,text,true,10701,3,3,580
1463537155920,2465,Changes,200,OK,JMeter Users 1-1,text,true,87663,5,5,732
1463537155890,2698,Changes,200,OK,JMeter Users 1-2,text,true,87663,5,5,772
1463537157489,1099,Home Page,200,OK,JMeter Users 1-5,text,true,10701,5,5,904
1463537156429,2210,Changes,200,OK,JMeter Users 1-3,text,true,87663,5,5,242
1463537158640,225,Home Page,200,OK,JMeter Users 1-3,text,true,10701,5,5,45
1463537158386,780,Home Page,200,OK,JMeter Users 1-1,text,true,10701,5,5,455
1463537158866,774,Changes,200,OK,JMeter Users 1-3,text,true,87663,5,5,50
1463537156477,3349,Home Page,200,OK,JMeter Users 1-4,text,true,10701,4,4,1015
1463537158588,1283,Home Page,200,OK,JMeter Users 1-2,text,true,10701,4,4,571
1463537159166,1170,Changes,200,OK,JMeter Users 1-1,text,true,87663,4,4,255
1463537159872,1139,Changes,200,OK,JMeter Users 1-2,text,true,87663,3,3,295
1463537159826,1670,Changes,200,OK,JMeter Users 1-4,text,true,87663,2,2,305
1463537161496,102,Home Page,200,OK,JMeter Users 1-4,text,true,10701,2,2,44
1463537161599,578,Changes,200,OK,JMeter Users 1-4,text,true,87663,2,2,45
1463537158589,4133,Changes,200,OK,JMeter Users 1-5,text,true,87663,1,1,3599
1463537162723,103,Home Page,200,OK,JMeter Users 1-5,text,true,10701,1,1,45
1463537162827,577,Changes,200,OK,JMeter Users 1-5,text,true,87663,1,1,44
```

### Mengubah variabel konfigurasi di Test Plan langsung dari command line

Untuk dapat mengubah suatu variable yang kita set dengan menggunakan GUI dan ditulisa pada file konfigurasi (jmx) maka kita bisa mengisi suatu variable dengan format berikut:

```
${__P(<VARIABLE_NAME>,<DEFAULT_VALUE>)}
```

Untuk kemudian kita bisa meng-override pada command line dengan opsti `-J<VARIABLE_NAME>=<VALUE> seperti contoh berikut.

Misal kita set value dari **Number of Threads (users)** menjadi `${__P(users,5)}`

Seperti di gambar berikut:

![image](https://cloud.githubusercontent.com/assets/3068071/15345467/6d1ab940-1cd9-11e6-9078-ae45316335f8.png)

Kemudian kita bisa menjalankan perintah seperti berikut

```
./jmeter -Jusers=50 -n -t /tmp/jmeter/build-web-test-plan.jmx -l test-result2.jtl
```

Hasilnya adalah 50 users akses ke 2 page `Home page` dan `Changes` jadi 100 kali akses dan di loop selama 2 kali jadi 200 akses dari user.


```
./jmeter -Jusers=50 -n -t /tmp/jmeter/build-web-test-plan.jmx -l test-result2.jtl
Creating summariser <summary>
Created the tree successfully using /tmp/jmeter/build-web-test-plan.jmx
Starting the test @ Wed May 18 09:18:52 WIB 2016 (1463537932460)
Waiting for possible shutdown message on port 4445
summary +     31 in   7.5s =    4.1/s Avg:  2110 Min:   641 Max:  4676 Err:     0 (0.00%) Active: 50 Started: 50 Finished: 0
summary +     85 in    30s =    2.8/s Avg: 13554 Min:  1173 Max: 32996 Err:     0 (0.00%) Active: 50 Started: 50 Finished: 0
summary =    116 in  37.5s =    3.1/s Avg: 10496 Min:   641 Max: 32996 Err:     0 (0.00%)
summary +     84 in  27.2s =    3.1/s Avg: 18733 Min:  1497 Max: 51908 Err:     0 (0.00%) Active: 0 Started: 50 Finished: 50
summary =    200 in    65s =    3.1/s Avg: 13955 Min:   641 Max: 51908 Err:     0 (0.00%)
Tidying up ...    @ Wed May 18 09:19:57 WIB 2016 (1463537997178)
... end of run
```

### Melihat hasil report (file jtl)

Jalankan JMeter GUI

Tambahkan pada Test Plan, sebuah elemen tipe Listerner misalnya "Summary Result" dan "View Result Tree", sesuai dari report apa yang ingin kita lihat.

Klik tombol [Browse] pada Summary Report window lalu pilih file JMeter log (misalnya `/tmp/jmeter/test-result2.jtl`)

![image](https://cloud.githubusercontent.com/assets/3068071/15345814/89ed1448-1cdc-11e6-8be4-e04ab017fa81.png)

Log file akan diload oleh JMeter dan kita bisa lihat report-nya, hal yang sama bisa kita lakukan pada "View Result Tree" report. 

Pada "View Result Tree" saat kita klik setiap sample request-response, kita hanya bisa melihat Sampler Result tab, sedangkan data detail pada Request dan Response Data tab tidak ada (kosong) karena file jtl tidak menyimpan data dengan lengkap untuk setiap sample request-response HTTP. 

> JMeter secara detail tidak menyimpan semua data hasil test karena akan memberatkan disk I/O saat menulis data tersebut ke log file


![image](https://cloud.githubusercontent.com/assets/3068071/15345872/dcdd65cc-1cdc-11e6-829a-c9951769d40c.png)

Untuk mendapatkan report yang lebih detail, saat menjalankan JMeter kita bisa menambahkan argumen seperti berikut:

```
-Jjmeter.save.saveservice.output_format=xml 
-Jjmeter.save.saveservice.samplerData=true 
-Jjmeter.save.saveservice.response_data=true
```

Hasilnya adalah sebuah file jtl dengan formal XML dan detail data request dan response
```
$ ./jmeter -Jusers=10 -Jjmeter.save.saveservice.output_format=xml -Jjmeter.save.saveservice.samplerData=true -Jjmeter.save.saveservice.response_data=true -n -t /tmp/jmeter/build-web-test-plan.jmx -l /tmp/jmeter/test-result2.jtl
Creating summariser <summary>
Created the tree successfully using /tmp/jmeter/build-web-test-plan.jmx
Starting the test @ Wed May 18 09:52:28 WIB 2016 (1463539948133)
Waiting for possible shutdown message on port 4445
summary +      4 in     2s =    2.2/s Avg:   582 Min:   210 Max:  1025 Err:     0 (0.00%) Active: 4 Started: 4 Finished: 0
summary +     36 in  11.3s =    3.2/s Avg:  1855 Min:   168 Max:  9204 Err:     0 (0.00%) Active: 0 Started: 10 Finished: 10
summary =     40 in  13.1s =    3.0/s Avg:  1727 Min:   168 Max:  9204 Err:     0 (0.00%)
Tidying up ...    @ Wed May 18 09:52:41 WIB 2016 (1463539961356)
... end of run
```

Sekarang cek file `/tmp/jmeter/test-result2.jtl` hasilnya menjadi file XML

```
$ head -5 /tmp/jmeter/test-result2.jtl
<?xml version="1.0" encoding="UTF-8"?>
<testResults version="1.2">
<httpSample t="313" lt="284" ts="1463539845156" s="true" lb="Home Page" rc="200" rm="OK" tn="JMeter Users 1-1" dt="text" by="10702" ng="2" na="2">
  <responseData class="java.lang.String">&lt;!DOCTYPE html SYSTEM &quot;about:legacy-compat&quot;&gt;
&lt;html lang=&quot;en&quot;&gt;&lt;head&gt;&lt;META http-equiv=&quot;Content-Type&quot; content=&quot;text/html; charset=iso-8859-15&quot;&gt;&lt;title&gt;Apache JMeter
```

Dan jika kita load pada JMeter GUI, kita bisa lihat detail request dan response data-nya.







