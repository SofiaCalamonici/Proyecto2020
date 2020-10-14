# Proyecto2020
Vincha lectora de ondas cerebrales

#include <Brain.h>

Brain brain(Serial);
int LED1 = 2;
int LED2 = 3;
int LED3 = 4;

void setup() {
 
pinMode(LED1, OUTPUT);
pinMode(LED2, OUTPUT);
pinMode(LED3, OUTPUT);

  Serial.begin(9600);
}

void loop() {
if(brain.update()){
    Serial.println(brain.readCSV());
}
  if(brain.readSignalQuality() > 80) {
 
 
     if (brain.readAttention() > 10){
      digitalWrite(LED1, HIGH);
      if (brain.readAttention() > 50){
      digitalWrite(LED2, HIGH);
      if (brain.readAttention() > 90){
      digitalWrite(LED3, HIGH);
    }
  }
}
  }
}
