# Potenciometro-arduino
int pot1 = A0;
int pot2 = A1;
int pot3 = A2;

int val1;
int val2;
int val3;

int r = 8;
int g = 9;
int b = 10;

void setup() {
  Serial.begin(9600);

  pinMode(pot1,INPUT);
  pinMode(pot2,INPUT);
  pinMode(pot3,INPUT);

  pinMode(r, OUTPUT);
  pinMode(g, OUTPUT);
  pinMode(b, OUTPUT);
}

void loop() {
  
  val1 = analogRead(pot1)/4;
  val2 = analogRead(pot2)/4;
  val3 = analogRead(pot3)/4;

  Serial.print(val1);
  Serial.print("/");
  Serial.print(val2);
  Serial.print("/");
  Serial.println(val3);

  analogWrite(r, val1);
  analogWrite(g, val2);
  analogWrite(b, val3);
  
  delay(0.01);

  
}
