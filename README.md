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



**HARDWARE**<br>
**IR SENSOR**<br>
int ir=D5;<br>
int led=D6;
void setup() {<br>
  // put your setup code here, to run once:<br>
  pinMode(ir,INPUT);<br>
    pinMode(led,OUTPUT);<br>
    Serial.begin(9600);<br>
    
}<br>

void loop() {<br>
  // put your main code here, to run repeatedly:<br>
  int irvalue=digitalRead(ir);<br>
  if(irvalue==LOW)<br>
  {<br>
    Serial.println("LOW");<br>
    digitalWrite(led,HIGH);<br>
  }<br>
  else<br>
  {<br>
    Serial.println("HIGH");<br>
    digitalWrite(led,LOW);<br>
  }<br>
delay(100);<br>
}<br>

</br>
Chassing LED<br>
int pinsCount=7; // declaring the integer variable pinsCount<br>
int pins[] = {D0,D1,D2,D3,D4,D5,D6}; // declaring the array pins[]<br>

void setup() {<br>
for (int i=0; i<pinsCount; i=i+1){ // counting the variable i from 0 to 9<br>
pinMode(pins[i], OUTPUT); // initialising the pin at index i of the array of pins as OUTPUT<br>
}<br>
}<br>
void loop() {<br>
for (int i=0; i<pinsCount; i=i+1){ // chasing right<br>
digitalWrite(pins[i], HIGH); // switching the LED at index i on<br>
delay(100); // stopping the program for 100 milliseconds<br>
digitalWrite(pins[i], LOW); // switching the LED at index i off<br>
}
for (int i=pinsCount-1; i>0; i=i-1){ // chasing left (except the outer leds)<br>
digitalWrite(pins[i], HIGH); // switching the LED at index i on<br>
delay(100); // stopping the program for 100 milliseconds<br>
digitalWrite(pins[i], LOW); // switching the LED at index i off<br>

}<br>
}<br>


IDR SENSOR<br>
int ldr=A0;//Set A0(Analog Input) for LDR.<br>

int value=0;<br>

int led=D1;<br>

void setup() {<br>

Serial.begin(9600);<br>

pinMode(led,OUTPUT);<br>

}<br>


void loop() {<br>

value=analogRead(ldr);//Reads the Value of LDR(light).<br>

Serial.println("LDR value is :");//Prints the value of LDR to Serial Monitor.<br>
<br>
Serial.println(value);<br>

if(value<50)<br>

{<br>
digitalWrite(led,HIGH);//Makes the LED glow in Dark.<br>
}<br>
else<br>
{<br>
digitalWrite(led,LOW);//Turns the LED OFF in Light.<br>
}<br>
delay(1000);<br>
}<br>

Sound Sensor<br>
int led = D6;<br>
int sound_digital = D2;<br>
//int sound_analog = A0;<br>

void setup(){<br>
  Serial.begin(9600);<br>
  pinMode(led, OUTPUT);<br>
  pinMode(sound_digital, INPUT);  <br>
}<br>

void loop(){<br>
  int val_digital = digitalRead(sound_digital);<br>
  //int val_analog = analogRead(sound_analog);<br>
<br>
  //Serial.print(val_analog);<br>
  Serial.print("\t");<br>
  Serial.println(val_digital);<br>

  if (val_digital == HIGH)<br>
  {<br>
    digitalWrite (led, HIGH);<br>
    delay(500);<br>
    }<br>
  else<br>
  {
    digitalWrite (led, LOW);<br>
    }<br>
}<br>


Soil moisture<br>
const int sensor_pin = A0;  /* Connect Soil moisture analog sensor pin to A0 of NodeMCU */<br>

void setup() {<br>
  Serial.begin(9600); /* Define baud rate for serial communication */<br>
}<br>

void loop() {<br>
  float moisture_percentage;<br>

  moisture_percentage = ( 100.00 - ( (analogRead(sensor_pin)/1023.00) * 100.00 ) );<br>

  Serial.print("Soil Moisture(in Percentage) = ");<br>
  Serial.print(moisture_percentage);
  Serial.println("%");<br>

  delay(1000);<br>
}<br>
<br>
1 internal exam<br>
https://wokwi.com/projects/333796636268429907 - LED<br>
https://wokwi.com/projects/333802415714206291 - 3 LED<br>
https://wokwi.com/projects/333801005399409236 - RGB Led<br>
https://wokwi.com/projects/340854134524609107-RGB ESP<br>
https://wokwi.com/projects/322062421191557714 - LIQUID CRYSTAL<br>
https://wokwi.com/projects/335699264816546387 - Servo Motor + Pushbutton<br>
https://wokwi.com/projects/334981582917993044 - Servo Motor + Sliding Potentiometer<br>
https://wokwi.com/projects/335069089200341587 - Buzzer + Pushbutton_<br>
https://wokwi.com/projects/335073264458007124 - Buzzer + UltraSonic Sensor<br>
https://wokwi.com/projects/335701186493547091 - Potentiometer + LED<br>
https://wokwi.com/projects/337602684471214674 - DHT22(Humidity and Temperature sensor)<br>
https://wokwi.com/projects/340775764469219922 - LED_CHASER<br>
https://wokwi.com/projects/340776572602548818 - LDR<br>
https://wokwi.com/projects/340776926585029204 - LDR_LED<br>

esp32 based program<br>
1 https://wokwi.com/projects/340854134524609107 -rgb<br>
2 https://wokwi.com/projects/340854774227272276 - lcd<br>
3 https://wokwi.com/projects/340856223828017746 -servo with pushbutton<br>
4 https://wokwi.com/projects/340857406334435922 -buzzer with pushbutton<br>
5 [https://wokwi.com/projects/340857463914889810 ](https://wokwi.com/projects/340872721906795092)-servo with sliding potentiometer  esp32<br>
6 https://wokwi.com/projects/340857989669847634 -ultrasonic with buzzer<br>
7 https://wokwi.com/projects/336966830711112275 - LED<br>
8 https://wokwi.com/projects/336967978479256147 - 3 LED<br>
9 https://wokwi.com/projects/340889723195097684 - Potentiometer + LED<br>
10 https://wokwi.com/projects/340890798001226322 -DTH2 ot correct executed<br>
11 https://wokwi.com/projects/340891507727794771 -LED_CHASER<br>
13 https://wokwi.com/projects/340972516846600786 -LDR<br> 
14 https://wokwi.com/projects/340972863626412627 - LDR_LED<br>

lab program 12/09<br>
https://wokwi.com/projects/342585605441454676 -seven segment led<br>
https://wokwi.com/projects/342586202604438100 -joystick with led dot matrix<br>
https://wokwi.com/projects/322410731508073042 -DTH22<br>
https://wokwi.com/projects/290056311044833800 -Display distance on LCD screen with LED <br> 
Reference2: https://wokwi.com/projects/290043622233997832 -Display distance on LCD screen with buzzer<br>
https://wokwi.com/projects/342590457634619986 -Arduino LED Graph Bar - Move the potentiometer knob to control the LEDs Reference<br>
https://wokwi.com/projects/342589648838591060 -Electronic Safe, powered by an Arduino Uno. Reference<br>
