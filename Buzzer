
#define trigPin 6
#define echoPin 7
#define buzzerPin 8

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  pinMode(buzzerPin, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  long duration;
  int distance;

  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  duration = pulseIn(echoPin, HIGH);
  distance = duration * 0.034 / 2;

  Serial.print("Distance: ");
  Serial.println(distance);

  if (distance > 15) {
    // Police siren tone with passive buzzer
    for (int i = 500; i < 1000; i += 10) {
      tone(buzzerPin, i);
      delay(5);
    }
    for (int i = 1000; i > 500; i -= 10) {
      tone(buzzerPin, i);
      delay(5);
    }
  } else {
    noTone(buzzerPin);
  }

  delay(100);
}
