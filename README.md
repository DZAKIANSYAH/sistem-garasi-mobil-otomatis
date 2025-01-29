# Sistem Garasi Mobil Otomatis
## _Sistem Garasi Mobil Otomatis berbasis arduino_
Sistem sensor garasi mobil adalah teknologi otomatis yang dirancang untuk meningkatkan keamanan, kenyamanan, dan efisiensi penggunaan garasi. Sistem ini biasanya menggunakan berbagai jenis sensor, seperti sensor ultrasonik, inframerah, atau magnetik, untuk mendeteksi keberadaan kendaraan, mengukur jarak, atau memantau kondisi pintu garasi.
# Fitur Utama:
1.	Pendeteksi Kendaraan
Sensor dapat mendeteksi keberadaan mobil saat memasuki atau meninggalkan garasi, memastikan pintu terbuka dan tertutup secara otomatis.
2.	Keamanan Pintar
Sistem dilengkapi dengan teknologi yang memungkinkan deteksi gangguan atau akses yang tidak sah, seperti alarm jika ada gerakan mencurigakan.
3.	Kontrol Otomatis Pintu Garasi
Dengan sensor jarak, pintu garasi dapat dibuka dan ditutup secara otomatis saat kendaraan mendekat atau menjauh.
4.	Integrasi dengan Smart Home
Sistem sensor ini dapat diintegrasikan dengan perangkat rumah pintar, seperti smartphone atau asisten suara, sehingga pengguna dapat memantau dan mengontrol garasi dari jarak jauh.
5.	Pemantauan Lingkungan
Beberapa sistem canggih memiliki sensor tambahan untuk mendeteksi suhu, kelembaban, atau keberadaan gas berbahaya, memberikan perlindungan ekstra bagi kendaraan dan penghuni rumah.

# Manfaat Sistem Sensor Garasi Mobil:
•	Keamanan Meningkat: Mencegah pencurian atau akses ilegal ke garasi.

•	Efisiensi Waktu: Proses otomatisasi mengurangi waktu yang dihabiskan untuk membuka dan menutup pintu garasi secara manual.

•	Mudah Digunakan: Sistem modern sering kali memiliki antarmuka yang ramah pengguna, baik melalui aplikasi atau kontrol suara.

Sistem sensor garasi mobil ini sangat cocok untuk rumah modern yang mengutamakan keamanan, kenyamanan, dan teknologi terkini.

## code

```sh
#include <Servo.h>
Servo servo;
int angle = 10;
// defines pins numbers
const int trigpin = 12;
const int echopin = 11;
// defines variables
long duration;
int distance;
void setup() {
	servo.attach(8);
	servo.write(angle);
pinMode(trigPin, OUTPUT); // Sets the trigpin as an Output
pinMode(echopin, INPUT); // Sets the echopin as an Input 
	Serial.begin(9600); // Starts the serial communication
}
void loop() {
// Clears the trigpin
digitalWrite(trigpin, LOW);
delayMicroseconds(2);
// Sets the trigPin on HIGH state for 10 micro seconds
digitalWrite(trigpin, HIGH);
delayMicroseconds(10);
digitalWrite(trigpin, LOW);
// Reads the echopin, returns the sound wave travel time in microseconds
duration pulseIn(echopin, HIGH);
// Calculating the distance
distance duration 0.034/2;
// Prints the distance on the Serial Monitor 
Serial.print("Distance: ");
Serial.println(distance);
delay(10);
	
if(distance<20)
{
servo.write(180); 
delay(3000);
}
else
{
servo.write(0);
{
}
```
# Implementasi
## Burn Bootloader Arduino
Untuk meng-upload Bootloader Arduino, kali ini digunakan Arduino lain sebagai ISP (In-System Program). Sebenarnya, akan lebih baik apabila menggunakan device yang lebih proper seperti USB-ASP, namun kali ini memanfaatkan resource yang telah tersedia (meminjam Arduino Uno punya teman).
Rangkaian untuk mem-burn Bootloader dapat dilihat seperti gambar dibawah. Intinya adalah menghubungkan pin SCK, MOSI, dan MISO, kontrol untuk Reset, dan pastinya catu daya 5V dan kristal osilator.
 ![alt text](https://github.com/DZAKIANSYAH/sistem-garasi-mobil-otomatis/blob/main/Screenshot%202025-01-27%20203528.png?raw=true)
## Upload The Code

Library yang dibutuhkan telah tersedia pada Arduino IDE. Pertama, adalah mengupload program ISP pada Arduino yang telah ada. Dapat dilakukan dengan cara memilih pada menu File > Examples > Arduino ISP > Arduino ISP lalu upload kode tersebut. Kemudian hubungkan seperti rangkaian diatas, lalu upload Bootloader pada menu Tools > Programmer > Arduino as ISP dan Tools > Burn Bootloader.
Setelah bootloader ter-install, prosedur untuk mengupload ke Arduino Clone seperti mengupload kode Arduino biasa. Namun, karena Arduino Clone yang dibuat ini tidak memiliki USB Decoder untuk komunikasi Serial yang dibutuhkan untuk mengupload Kode ke Arduino Clone, digunakan FTDI USB Serial.


**Free Software, Hell Yeah!**

[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)

   [dill]: <https://github.com/joemccann/dillinger>
   [git-repo-url]: <https://github.com/joemccann/dillinger.git>
   [john gruber]: <http://daringfireball.net>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [markdown-it]: <https://github.com/markdown-it/markdown-it>
   [Ace Editor]: <http://ace.ajax.org>
   [node.js]: <http://nodejs.org>
   [Twitter Bootstrap]: <http://twitter.github.com/bootstrap/>
   [jQuery]: <http://jquery.com>
   [@tjholowaychuk]: <http://twitter.com/tjholowaychuk>
   [express]: <http://expressjs.com>
   [AngularJS]: <http://angularjs.org>
   [Gulp]: <http://gulpjs.com>

   [PlDb]: <https://github.com/joemccann/dillinger/tree/master/plugins/dropbox/README.md>
   [PlGh]: <https://github.com/joemccann/dillinger/tree/master/plugins/github/README.md>
   [PlGd]: <https://github.com/joemccann/dillinger/tree/master/plugins/googledrive/README.md>
   [PlOd]: <https://github.com/joemccann/dillinger/tree/master/plugins/onedrive/README.md>
   [PlMe]: <https://github.com/joemccann/dillinger/tree/master/plugins/medium/README.md>
   [PlGa]: <https://github.com/RahulHP/dillinger/blob/master/plugins/googleanalytics/README.md>
  
