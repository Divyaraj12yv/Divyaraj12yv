const int sensorPin = A0;       
const int ledPin = 6;           
const int potPin = A1;          

int sensorValue = 0;            
int brightness = 0;             
int potValue = 0;               
void setup() {
  pinMode(ledPin, OUTPUT);      
  Serial.begin(9600);          
}

void loop() {
  sensorValue = analogRead(sensorPin);  
  potValue = analogRead(potPin);        

  
  brightness = map(potValue, 0, 1023, 0, 255);
  
  analogWrite(ledPin, brightness);

  Serial.print("Sensor Value: ");
  Serial.println(sensorValue);
  Serial.print("Brightness: ");
  Serial.println(brightness);

  delay(1000);  



 
