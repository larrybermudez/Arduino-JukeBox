# Arduino-JukeBox
JukeBox made using an Arduino Uno, piezo buzzer and a few buttons and an LCD Display

What is it?

This project was intended to demonstrate my understanding user input and output and also how to use external libraries or files into a single project.

How does it work?

- An 16x2 LCD Display was connected to pins on an Arduino Board to obtain information when a user pushes either button to display information, in this case the Song Name. A potentiometer was also used to adjust the bias level in the lcd display. 
- 2 buttons were connected to the board. When the left one is pressed, the Song Name pops up in the lcd screen and when the right button is pushed, the song is played and once it is over, adds the text "End of Song" for 5 seconds before the lcd screen is cleared.
- The buttons were also programmed to take advantage of the Arduino's built in pull-resistor output so that we can save the digital reading to know when the buttons have been pushed.
- Lastly, the Piezo Buzzer was used to play the music notes which the pitches.h file was used to define each Music Note to their corresponding frequences. 
