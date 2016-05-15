#LAB1: Instalasi JMeter

Pada dasarnya instalasi JMeter hanya perlu mengekstrak binary (file ZIP atau TGZ), selesai!

1. Instal JRE/JDK
   
   Download JDK/JRE dari [Oracle website](http://www.oracle.com/technetwork/java/javase/downloads/index.html) atau [Azul website](http://www.azul.com/downloads/zulu/).
   
   Setting environment variable `JAVA_HOME` dan `PATH`
   
   Test dari command line (shell) dengan perintah `java -version`

2. Download JMeter 
   
   Download binary package (file ZIP atau TGZ) dari [Apache JMeter website](http://jmeter.apache.org/download_jmeter.cgi), atau download 
   langsung dari link berikut untuk versi 2.13 (versi terakhir saat tulisan ini dibuat)
   
   [http://www-us.apache.org/dist//jmeter/binaries/apache-jmeter-2.13.zip](http://www-us.apache.org/dist//jmeter/binaries/apache-jmeter-2.13.zip)
   
   ![image](https://cloud.githubusercontent.com/assets/3068071/15264994/06d1fea0-19a5-11e6-81b2-63dc83546a21.png)
   
3. Ekstrak file `apache-jmeter-2.13.zip`
   
   Kita akan instal jmeter di direktori `/home/jmeter/apache-jmeter-2.13/`
   
   Secara default, akan dibuat direktori dengan nama `apache-jmeter-X.Y` saat ekstrak file ZIP. 
   
   Buka shell terminal, lalu jalankan perintah berikut:
   
   ```
   mkdir /home/jmeter
   unzip apache-jmeter-2.13.zip -d /home/jmeter
   ```
   
   Hasilnya di direktori tersebut 
   
   ```
   bin/             : direktori yang berisisi perintah-perintah yang bisa dijalankan
   docs/            : dokumentasi Java API
   extras/          :
   lib/             :
   lib/ext/         :
   lib/junit/       : 
   licenses/        : lisensi
   printable_docs/  : dokumentasi (user manual)
   ```
   
4. Menjalankan JMeter
   
   Untuk menjalankan JMeter dengan mode GUI kita hanya perlu mengeksekusi file `bin/jmeter.sh` atau `bin/jmeter`
   Jika menggunakan Windows file anda dapat men-double-click file `bin\jmeter.bat` atau `bin\jmeterw.bat`
   
   ```
   cd /home/jmeter/apache-jmeter-2.13/bin
   ./jmeter.sh
   ```
   
   Hasilnya Jmeter window akan muncul seperti ini:
   
   ![image](https://cloud.githubusercontent.com/assets/3068071/15265250/d4ccfd56-19a9-11e6-813b-2be30b9fdfbf.png)
   
