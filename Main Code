#include <LiquidCrystal.h>
#include "pitches.h"

// Define buttons, speaker and lcd pins

const int left_btn_pin = 8;
const int right_btn_pin = 9;
const int speaker_pin = 6;

LiquidCrystal lcd(12, 11, 2, 3, 4, 5);

// Define notes of song:
int melody[] = {
  NOTE_AS4, REST, NOTE_AS4, REST, NOTE_AS4, REST, NOTE_AS4, REST,
  NOTE_AS4, NOTE_B4, NOTE_DS5,
  NOTE_AS4, REST, NOTE_AS4, REST,
  NOTE_AS4, NOTE_B4, NOTE_DS5,
  NOTE_AS4, REST, NOTE_AS4, REST,
  NOTE_AS4, NOTE_B4, NOTE_DS5,
  NOTE_AS4, REST, NOTE_AS4, REST,
  NOTE_AS4, NOTE_B4, NOTE_DS5,
  NOTE_F5, REST, NOTE_F5, REST,
  NOTE_GS5, NOTE_FS5, NOTE_F5,
  NOTE_AS4, REST, NOTE_AS4, REST,
  NOTE_GS5, NOTE_FS5, NOTE_F5,
  NOTE_AS4, REST, NOTE_AS4, REST,
  NOTE_AS4, NOTE_B4, NOTE_DS5,
  NOTE_AS4, REST, NOTE_AS4, REST,
  NOTE_AS4, NOTE_B4, NOTE_DS5,
  NOTE_AS4, REST, NOTE_AS4, REST,
  REST
};

int durations[] = {
  4, 4, 4, 4, 4, 4, 4, 4,
  3, 3, 4,
  4, 4, 4, 4,
  3, 3, 4,
  4, 4, 4, 4,
  3, 3, 4,
  4, 4, 4, 4,
  3, 3, 4,
  4, 4, 4, 4,
  3, 3, 4,
  4, 4, 4, 4,
  3, 3, 4,
  4, 4, 4, 4,
  3, 3, 4,
  4, 4, 4, 4,
  3, 3, 4,
  4, 4, 4, 4,
  1
};

// Set btn settings

int left_prev = HIGH;
int right_prev = HIGH;
 
void setup() {
  //Set PinMode and LCD Display
  pinMode(speaker_pin, OUTPUT);
  pinMode(left_btn_pin, INPUT_PULLUP);
  pinMode(right_btn_pin, INPUT_PULLUP);

  lcd.begin(16, 2);
  lcd.clear();

}
 
void loop() {
  
  int left_state = digitalRead(left_btn_pin);
  
  //Set up lcd screen if btn is pressed
  if ( (left_prev == HIGH) && (left_state == LOW) ) {
    lcd.print("Tokyo Drift");
  } 
  
  int right_state = digitalRead(right_btn_pin);
  // Play song if right button is pressed
  if ( (right_prev == HIGH) && (right_state == LOW) ) {
    int size = sizeof(durations) / sizeof(int);
    for (int note = 0; note < size; note++) {
    //to calculate the note duration, take one second divided by the note type.
      int duration = 1000 / durations[note];
      tone(speaker_pin, melody[note], duration);

    //distinguish the different notes
      int pauseBetweenNotes = duration * 1.30;
      delay(pauseBetweenNotes);
    
    //stop the tone playing:
      noTone(speaker_pin);
      
    }
    // display when the song ends
    lcd.setCursor(0, 1);
    lcd.print("End of Song");
    delay(5000);
    lcd.clear();
    
  }
  left_prev = left_state;
  right_prev = right_state;
}






