# GAS-LEAK-DETECTION-SYSTEM-USING-GAS-SENSOR

## Aim:
	To measure the air quality using Gas Sensor  MQ-2 with Arduino UNO Board/ESP-32 using Tinker CAD.
To measure the air quality using Gas Sensor  MQ-2 with Arduino UNO Board/ESP-32 using Tinker CAD.

## Hardware / Software Tools required:
PC/ Laptop with Internet connection
  Tinker CAD tool (Online)
	Tinker CAD tool (Online)
Arduino UNO Board/ESP-32
  Gas sensor (MQ-2)
	Gas sensor (MQ-2)

## Circuit Diagram:

 



<img width="1162" height="612" alt="image" src="https://github.com/user-attachments/assets/6ccb0bb9-94cd-488d-827e-c23d04f31a8a" />

## Theory :
The Arduino Uno is powered by the ATmega328P, an 8-bit microcontroller that runs at 16 MHz. It has 32 KB of flash memory, 2 KB of SRAM, and 1 KB of EEPROM. The board 
@@ -57,10 +54,52 @@ Step 7: Save Your Work
•	Save the Circuit: Click "Save" to keep your circuit design and code for future use.

## Program:
```
#include <LiquidCrystal.h>
// initialize the library with the numbers of the interface pins
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);
void setup() {
  Serial.begin(9600);
  // set up the LCD's number of columns and rows:
  lcd.begin(16, 2);
  pinMode(13,OUTPUT);
  pinMode(7,OUTPUT);
  pinMode(6,OUTPUT);
}
void loop() {
  int gas_data;
  gas_data = analogRead(A0);
  lcd.setCursor(00,00);
  lcd.print("Gas :");
  lcd.setCursor(6,00);
  lcd.print(gas_data);
  if(gas_data > 800){
  	digitalWrite(13,HIGH);
    delay(100);
    digitalWrite(13,LOW);
    lcd.setCursor(00,1);
    lcd.print("DANGER");
  }else if(gas_data > 700){
    digitalWrite(6,HIGH);
  	delay(100);
    digitalWrite(6,LOW);
    lcd.setCursor(00,1);
    lcd.print("WARNING");
  }else {
    digitalWrite(7,HIGH);
    lcd.setCursor(00,1);
    lcd.print("SAFE");
  }
  Serial.println(gas_data);
  delay(100);
  lcd.clear();
}
```

## Output:

<img width="1137" height="603" alt="image" src="https://github.com/user-attachments/assets/432d24f5-0c53-4de4-8e73-2341c6b24a7b" />


## Result:
The quality of air is measured using Gas Sensor MQ-2 with Arduino UNO Board/ESP-32 using Tinker CAD Verified Successfully.
