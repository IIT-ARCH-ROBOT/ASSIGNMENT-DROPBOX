Using C++ language and particle.io website this was the final code:

```C++
Timer sitTimer(5000, tooLong);

int track1 = 0;
int track2 = 1;
int buttonPin = 6;

void setup() {
    pinMode(buttonPin, INPUT_PULLDOWN);
    pinMode(7, OUTPUT);
    pinMode(track1, OUTPUT);
    pinMode(track2, OUTPUT);
    digitalWrite(track1, HIGH);
    digitalWrite(track2, HIGH);
    digitalWrite(7, LOW);
}

void loop() {
    
    if(digitalRead(buttonPin)){
        digitalWrite(7, HIGH);
        trigger_sound(track1);
        sitTimer.start();
    }
    
}

void trigger_sound(int pin){
    digitalWrite(pin, LOW);
    delay(100);
    digitalWrite(pin, HIGH);
}

void tooLong(){
    trigger_sound(track2);
    sitTimer.stop();
    digitalWrite(7, LOW);
}
```
