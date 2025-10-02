#include <Servo.h>

Servo Motorzinho;

int pinoLed = 12;
int pinoSensor = 8;
int led = 6; // Alterado para um pino com PWM

void setup() {
  Motorzinho.attach(9);
  pinMode(led, OUTPUT);
  pinMode(pinoSensor, INPUT);
  pinMode(pinoLed, OUTPUT);
  digitalWrite(pinoLed, LOW);
}

void loop() {
  // Verifica o sensor
  if (digitalRead(pinoSensor) == LOW) {
    digitalWrite(pinoLed, HIGH);
  } else {
    digitalWrite(pinoLed, LOW);
  }

  // Movimento do servo motor
  Motorzinho.write(0);
  delay(500);
  Motorzinho.write(180);
  delay(500);

  // Acender LED gradativamente
  for (int contador = 0; contador <= 255; contador++) {
    analogWrite(led, contador);
    delay(3);
  }

  // Apagar LED gradativamente
  for (int contador = 255; contador >= 0; contador--) {
    analogWrite(led, contador);
    delay(3);
  }

  delay(1000);
}
