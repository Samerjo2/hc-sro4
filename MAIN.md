#define trigPin 11
#define echoPin 12
long duration, distance; 
void setup() { 
Serial.begin (9600);
pinMode(trigPin, OUTPUT); 
pinMode(echoPin, INPUT); 
} 
void loop() {
digitalWrite(trigPin, LOW); 
delayMicroseconds(100); 
digitalWrite(trigPin, HIGH); 
delayMicroseconds(100); 
digitalWrite(trigPin, LOW);
duration = pulseIn(echoPin, HIGH);
distance = (duration/2) * 0.0343; // 343 * (100/1000000) = 343/10000 
Serial.println(distance);
delay(200);
}
