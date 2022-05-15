# Line-follower-bot
This bot will follow a line of different color(black) with respect to ground. Using infra_red sensor i developed the project.

<p align="center">
  <img 
    height="350"
    src="Images/LineFollow img.jpg"
  >
</p>

### Coding:
```
/*-------definning Inputs------*/
int LS = 2;      // left sensor
int RS = 4;      // right sensor
int LM1 = 5;       // left motor
int LM2 = 6;       // left motor
int RM1 = 9;       // right motor
int RM2 = 10;      // right motor
void setup()
{
  pinMode(LS, INPUT);
  pinMode(RS, INPUT);
  pinMode(LM1, OUTPUT);
  pinMode(LM2, OUTPUT);
  pinMode(RM1, OUTPUT);
  pinMode(RM2, OUTPUT);

}
void loop()
{
  if(!digitalRead(LS) && !digitalRead(RS))     // Move Forward

  {
    analogWrite(LM1, 170);
    digitalWrite(LM2, LOW);
    analogWrite(RM1, 170);
    digitalWrite(RM2, LOW);
  }
  
  if((digitalRead(LS)) && !digitalRead(RS))     // Turn right
  {
    analogWrite(LM1, LOW);
    digitalWrite(LM2, LOW);
    analogWrite(RM1, 180);
    digitalWrite(RM2, LOW);
    delay(25);
  }
  
  if(!digitalRead(LS) && (digitalRead(RS)))     // turn left
  {
    analogWrite(LM1, 180);
    digitalWrite(LM2, LOW);
    analogWrite(RM1, LOW);
    digitalWrite(RM2, LOW);
    delay(25);
  } 
  
  if((digitalRead(LS)) && (digitalRead(RS)))     // stop
  {
    analogWrite(LM1, LOW);
    digitalWrite(LM2, LOW);
    analogWrite(RM1, LOW);
    digitalWrite(RM2, LOW);
  }
}
```
