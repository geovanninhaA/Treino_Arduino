# Treino_Arduino
// ACENDER GRADATIVAMENTE
int led=11;
void setup() {
  pinMode(led,OUTPUT);

}

void loop() {
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

