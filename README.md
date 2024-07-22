# Ultrasonic-sensor
long duration;
int distance;
#define trigPin 3
#define echoPin 4
void setup() {
  // put your setup code here, to run once:
  pinMode (trigPin,OUTPUT);
  pinMode(echoPin, INPUT);
  Serial.begin(9600);


}

void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite(trigPin,LOW);
  delay(1000);
  digitalWrite(trigPin,HIGH);
  delay(1000);
  digitalWrite(trigPin,LOW);
  
  duration= pulseIn(echoPin,HIGH);
  distance= duration* 0.343/2;

  Serial.print('Distance =');
  Serial.println(distance);
  

}
