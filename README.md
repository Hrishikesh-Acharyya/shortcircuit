// C++ code
//

int buttonstate;
int LED_RED = 13;
int LED_YELLOW = 12;
int LED_GREEN = 8;
int BUTTON_PIN = 4;
int offset = 0;
void setup()
{
 
  pinMode(LED_RED, OUTPUT);
  pinMode(LED_YELLOW, OUTPUT);
  pinMode(LED_GREEN, OUTPUT);
  pinMode(BUTTON_PIN, INPUT);
  
}

void loop()
{
  buttonstate = digitalRead(BUTTON_PIN);
  
  if(buttonstate == 1){
      
  digitalWrite(LED_RED, HIGH);
 
  digitalWrite(LED_YELLOW, LOW);
  
  digitalWrite(LED_GREEN, LOW);
  
  }
 
 else if (buttonstate == 0){
	
   if(millis()-offset<3000)
   {
     digitalWrite(LED_RED,HIGH);
     digitalWrite(LED_YELLOW,LOW);
     digitalWrite(LED_GREEN,LOW);
   }
   
   else if(millis()-offset<4500 && millis()-offset>= 3000)
   {
     digitalWrite(LED_RED,LOW);
     digitalWrite(LED_YELLOW,HIGH);
     digitalWrite(LED_GREEN,LOW);
   }
   
   else{
     digitalWrite(LED_RED,LOW);
     digitalWrite(LED_YELLOW,LOW);
     digitalWrite(LED_GREEN,HIGH);
     delay(2000);
   }

 }
 
}
