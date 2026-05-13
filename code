//a password checker
#include <Keypad.h>

// can only be 1-9, A, B, C, D, *, or #
String password = "12345";

const byte r = 4; 
const byte c = 4; 

String triedpass = "";
int num = 0;

char keys[r][c] = {
  {'1','2','3','A'},
  {'4','5','6','B'},
  {'7','8','9','C'},
  {'*','0','#','D'}
};

// it's like when you enter a keypad to your door and the lights light up
int led1 = A0;
int led2 = A1;
int led3 = A2;
int led4 = A3;
int led5 = A4;

// right and wrong LEDs
int greenled = 11;
int redled = 10;

byte rowPins[r] = {9, 8, 7, 6};
byte colPins[c] = {5, 4, 3, 2};

Keypad keypad = Keypad(makeKeymap(keys), rowPins, colPins, r, c);

void setup() {
  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);
  pinMode(led3, OUTPUT);
  pinMode(led4, OUTPUT);
  pinMode(led5, OUTPUT);

  pinMode(greenled, OUTPUT);
  pinMode(redled, OUTPUT);

  Serial.begin(9600);
}

void loop() {
  char key = keypad.getKey();

  if (key) {
    if (key == '#') {
      triedpass = "";
    }
    else {
      triedpass += key;
    }
    
    Serial.println(triedpass);

    if (triedpass.length() == 1){
    digitalWrite(led1, HIGH);
    digitalWrite(led2, LOW);
    digitalWrite(led3, LOW);
    digitalWrite(led4, LOW);
    digitalWrite(led5, LOW);
    digitalWrite(greenled, LOW);
    digitalWrite(redled, LOW);
  }
  if (triedpass.length() == 2){
    digitalWrite(led1, HIGH);
    digitalWrite(led2, HIGH);
    digitalWrite(led3, LOW);
    digitalWrite(led4, LOW);
    digitalWrite(led5, LOW);
    digitalWrite(greenled, LOW);
    digitalWrite(redled, LOW);
  }
  if (triedpass.length() == 3){
    digitalWrite(led1, HIGH);
    digitalWrite(led2, HIGH);
    digitalWrite(led3, HIGH);
    digitalWrite(led4, LOW);
    digitalWrite(led5, LOW);
    digitalWrite(greenled, LOW);
    digitalWrite(redled, LOW);
  }
  if (triedpass.length() == 4){
    digitalWrite(led1, HIGH);
    digitalWrite(led2, HIGH);
    digitalWrite(led3, HIGH);
    digitalWrite(led4, HIGH);
    digitalWrite(led5, LOW);
    digitalWrite(greenled, LOW);
    digitalWrite(redled, LOW);
  }
  if (triedpass.length() == 5){
    if (triedpass == password) {
      digitalWrite(led1, HIGH);
      digitalWrite(led2, HIGH);
      digitalWrite(led3, HIGH);
      digitalWrite(led4, HIGH);
      digitalWrite(led5, HIGH);
      digitalWrite(greenled, HIGH);
      digitalWrite(redled, LOW);
    }
    else {
      digitalWrite(led1, LOW);
      digitalWrite(led2, LOW);
      digitalWrite(led3, LOW);
      digitalWrite(led4, LOW);
      digitalWrite(led5, LOW);
      digitalWrite(redled, HIGH);
      digitalWrite(greenled, LOW);
    }
    delay(1000);
    digitalWrite(led1, LOW);
    digitalWrite(led2, LOW);
    digitalWrite(led3, LOW);
    digitalWrite(led4, LOW);
    digitalWrite(led5, LOW);
    digitalWrite(redled, LOW);
    digitalWrite(greenled, LOW);
  }
  }
  if (triedpass.length() >= 5){
      triedpass = "";
    }
}
