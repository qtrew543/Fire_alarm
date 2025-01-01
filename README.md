# Fire_alarm
const int flameSensorPin = A0; 
const int buzzerPin = 8;       

const int flameThreshold = 400;

void setup() {
  Serial.begin(9600);

  pinMode(buzzerPin, OUTPUT);

  Serial.println("Fire Alarm System Initialized");
}

void loop() {
  int flameValue = analogRead(flameSensorPin);

  Serial.print("Flame Sensor Value: ");
  Serial.println(flameValue);

  if (flameValue < flameThreshold) {
    Serial.println("Flame Detected!");

    digitalWrite(buzzerPin, HIGH);
  } else {
    Serial.println("No Flame Detected.");

    digitalWrite(buzzerPin, LOW);
  }

  delay(500);
}
