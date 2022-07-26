PROGRAMS OF IOT<br>
1.Traffic LED<br>
https://wokwi.com/projects/333716331435131476<br>
2.RGB LED<br>
https://wokwi.com/projects/333805328840786515<br>
3.Hello world<br>
https://wokwi.com/projects/322062421191557714<br>
4.servometer<br>
https://wokwi.com/projects/334978042856211028<br>
5.servomotor using potential slide<br>
https://wokwi.com/projects/334978042856211028<br>
6.buzzer with resistor only<br>
https://wokwi.com/projects/335065104791896658<br>
7.using buzzer and pushbutton<br>
https://wokwi.com/projects/335067745393574483<br>
8.ultrasonic sensor<br>
https://wokwi.com/projects/335070015851070035<br>
9.ultrasonic sensor with buzzer<br>
https://wokwi.com/projects/335706592453329491<br>
10.ultrasonic sensor with buzzer and LED<br>
https://wokwi.com/projects/335610028297814611<br>
11.2 ultrasonic with one buzzer and LED<br>
https://wokwi.com/projects/335703435993154131<br>
12.Potentiometer with LED<br>
https://wokwi.com/projects/335701299799523922<br>



Hardware:<br>

DHT11<br>

#include <Adafruit_Sensor.h><br>
#include <DHT.h>;<br>
#define DHTPIN 13     // what pin we're connected to<br>
#define DHTTYPE DHT11   // DHT 22  (AM2302)<br>
DHT dht(DHTPIN, DHTTYPE); //// Initialize DHT sensor for normal 16mhz Arduino<br>
//Variables<br>
int chk;<br>
float hum;  //Stores humidity value<br>
float temp; //Stores temperature value<br>
void setup()<br>
{<br>
  Serial.begin(9600);<br>
  dht.begin();<br>
}<br>
void loop()<br>
{<br>
delay(2000);<br>
//Read data and store it to variables hum and temp<br>
hum = dht.readHumidity();<br>
temp= dht.readTemperature();<br>
//Print temp and humidity values to serial monitor<br>
Serial.print("Humidity: ");<br>
Serial.print(hum);<br>
Serial.print(" %, Temp: ");<br>
Serial.print(temp);<br>
Serial.println(" Celsius");<br>
delay(1000); //Delay 2 sec.<br>
}<br>



1.   https://wokwi.com/projects/338227139367141971      (1. to turn LED on for 1 sec after every 2 sec)<br>
2.   https://wokwi.com/projects/338226711455859284      (2. turn on the LED when pushbutton is pressed)<br>
3.   https://wokwi.com/projects/338147082096345683      (DHT22 humidity sensor with temperature)(s/w)<br>
4.   https://wokwi.com/projects/335705347315466835      (servomoter with pushbutton)<br>
5.   https://wokwi.com/projects/338154081559249491      (DHT22+LCD)(s/w)<br>

