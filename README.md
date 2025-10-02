# Treino_Arduino
#include<Servo.h>
Servo Motorzinho;
int led=13;
void setup() {
 Motorzinho.attach(9);
 pinMode(led,OUTPUT);

}

void loop() {
  Motorzinho.write(0);
  delay(500);
  Motorzinho.write(360);
  delay(500);
  //Acender led gradativamente
  for(int contador=0; contador<=255; contador++){
    analogWrite(led,contador);
    delay(3);
  }
  //apagar led gradativamente
  for(int contador=255; contador>=0; contador--){
    analogWrite(led,contador);
    delay(3);
  }
  delay(1000);
}
