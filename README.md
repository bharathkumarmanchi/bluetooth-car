# bluetooth-car
simple bluetooth rover using arduinoUNO
with the use of Bluetooth Module HC-05
connect the bluetooth module TX,RX to Arduino RX,TX respectively
use any app available in the play store and make sure of the settings in the app

// Starting of Program
int m1a = 9;
int m1b = 10;
int m2a = 11;
int m2b = 12;
char val;

void setup() 
{  
pinMode(m1a, OUTPUT);  // Digital pin 10 set as output Pin
pinMode(m1b, OUTPUT);  // Digital pin 11 set as output Pin
pinMode(m2a, OUTPUT);  // Digital pin 12 set as output Pin
pinMode(m2b, OUTPUT);  // Digital pin 13 set as output Pin
Serial.begin(9600);
}

void loop()
{
  while (Serial.available() > 0)
  {
  val = Serial.read();
  Serial.println(val);
  }

  if( val == 'f') // Forward
    {
      digitalWrite(m1a, HIGH);
      digitalWrite(m1b, LOW);
      digitalWrite(m2a, HIGH);
      digitalWrite(m2b, LOW);
      delay(5000);  
      digitalWrite(m1a, LOW);
      digitalWrite(m1b, LOW);
      digitalWrite(m2a, LOW);
      digitalWrite(m2b, LOW);
      
    }
  else if(val == 'b') // Backward
    {
      digitalWrite(m1a, LOW);
      digitalWrite(m1b, HIGH);
      digitalWrite(m2a, LOW);
      digitalWrite(m2b, HIGH); 
      delay(5000);  
      digitalWrite(m1a, LOW);
      digitalWrite(m1b, LOW);
      digitalWrite(m2a, LOW);
      digitalWrite(m2b, LOW);
    }
  
   else if(val == 'l') //Left
    {
    digitalWrite(m1a, LOW);
    digitalWrite(m1b, LOW);
    digitalWrite(m2a, HIGH);
    digitalWrite(m2b, LOW);
    delay(3000); 
    digitalWrite(m1a, LOW);
    digitalWrite(m1b, LOW);
    digitalWrite(m2a, LOW);
    digitalWrite(m2b, LOW);
    }
    else if(val == 'r') //Right
    {
    digitalWrite(m1a, HIGH);
    digitalWrite(m1b, LOW);
    digitalWrite(m2a, LOW);
    digitalWrite(m2b, LOW);
    delay(3000);  
    digitalWrite(m1a, LOW);
    digitalWrite(m1b, LOW);
    digitalWrite(m2a, LOW);
    digitalWrite(m2b, LOW); 
    }
    
  else if(val == 's') //Stop
    {
    digitalWrite(m1a, LOW);
    digitalWrite(m1b, LOW);
    digitalWrite(m2a, LOW);
    digitalWrite(m2b, LOW); 
    }
}
