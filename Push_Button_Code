const byte ledpin = 4;
const byte pushbuttonpin = 3;
int ledstate = LOW;
int debouncedelay = 50;
int lastbuttonstate = LOW;
int buttonstate = LOW;
unsigned long lastdebouncetime = 0;

void setup() 
{
 pinMode(ledpin,OUTPUT);
 pinMode(pushbuttonpin,INPUT);
}

void loop() 
{
  ButtonDebounce();
}

void ButtonDebounce()
{
  int readbutton = digitalRead(pushbuttonpin);
 
  if(lastbuttonstate != readbutton)
  {
    lastdebouncetime = millis();
  }
  if(millis() - lastdebouncetime > debouncedelay)
  {
   if(buttonstate!=readbutton) 
   {
     buttonstate = readbutton;
     if(buttonstate == HIGH)
     {
       ledstate = !ledstate;
     }
   }
  }
  
  digitalWrite(ledpin,ledstate);
  lastbuttonstate = readbutton;
}
void ButtonWithoutDebounce()
{
  int readbutton = digitalRead(pushbuttonpin);
 if(readbutton == HIGH)
 {
   ledstate = !ledstate;
 }
 digitalWrite(ledpin,ledstate);
}
