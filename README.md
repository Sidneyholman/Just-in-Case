
#include <LiquidCrystal.h>

// initialize the library by associating any needed LCD interface pin
// with the arduino pin number it is connected to
const int rs = 12, en = 11, d4 = 5, d5 = 4, d6 = 3, d7 = 2;
LiquidCrystal lcd(rs, en, d4, d5, d6, d7);

// button stuff
const int buttonPin = 6;
      //const int lcdPin; 
int buttonState;
  


void setup() {
  // set up the LCD's number of columns and rows:
      //lcd.begin(16, 2);
  
  //BUTTON
   pinMode(buttonPin, INPUT);
      //pinMode(lcdPin, OUTPUT);
  lcd.clear();
}

void loop() {
  lcd.setCursor(0, 1);
  
// EVERYTHING BEFORE THIS WORKS - BELOW IS BUTTONS

buttonState = digitalRead(buttonPin);
 if (buttonState == HIGH) {
    lcd.print("I'm okay");
    delay (2000);
    lcd.clear();
    
   //digitalWrite(lcdPin, HIGH);
   
  } else {
    
   //digitalWrite(lcdPin, LOW);
 }
 
 }

//The next part is the code for the Arduino Uno 

int greenCircuit = 2;
int redCircuit = 3;
int buttonRed = 7;
int buttonGreen = 8;
int valRed;
int valGreen;

void setup() {
  Serial.begin(9600);
  pinMode(greenCircuit, OUTPUT);
  pinMode(redCircuit, OUTPUT);
  pinMode(buttonRed, INPUT);
  pinMode(buttonGreen, INPUT);
}

void loop() {
  valRed = digitalRead(buttonRed);
  valGreen = digitalRead(buttonGreen);
  
  Serial.print("RED: ");
  Serial.println(valRed);
  Serial.print("GREEN: ");
  Serial.println(valGreen);
}

 
