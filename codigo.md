// C++ code
//

int ledVermelho = 10;
int ledVerde = 11;
int botao = 7;
int ciclo_do_led;

void setup()
{
  pinMode(botao, INPUT);
  pinMode(ledVermelho, OUTPUT);
  pinMode(ledVerde, OUTPUT);
  ciclo_do_led = 1;
}

void loop()
{
  if (digitalRead(botao) == HIGH) {
    if (ciclo_do_led == 1) {
      digitalWrite(ledVermelho, true);
      ciclo_do_led = 2;
      delay(100);
    } else if (ciclo_do_led == 2) {
      digitalWrite(ledVerde, true);
      digitalWrite(ledVermelho, false);
      ciclo_do_led = 3;
      delay(100);
    } else if (ciclo_do_led == 3) {
      digitalWrite(ledVerde, false);
      ciclo_do_led = 1;
      delay(100);
    }
  }
}
