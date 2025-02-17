# Digital Timer

Include your responses to the bold questions below. Include snippets of code that explain what you did. Deliverables are due next Tuesday. Post your lab reports as README.md pages on your GitHub, and post a link to that on your main class hub page.

## Part 0. Pre-lab 2
10 ideas:
1) Egg boiling alarm. Choose a desired setting, the timer will start accordingly. Play sound when finished:
    - Liquid boiled (4 mins)
    - Soft boiled (6 mins)
    - Hard boiled (8 mins)
2) Chess clock: for 2 chess players to monitor their time spent (example)
3) Reaction game: 2 players, 2 buttons. Who is faster to hit his button? Display accurate time in milisecond. 
4) Addition game: 2 players, 2 buttons, 2 stopwatch times displayed on screen. There is a third time called “Total time”, which is the sum of the 2 stopwatch times. Players keep pressing buttons until the sum is a rounded number (e.g. 2 mins 0 seconds)
5) Hour announcer: Play a different sound / light up a different LED whenever the clock reaches a new hour.
6) Stand-up reminder: Remind you to stand up for 1 minute every 1 hour
7) World clock
8) Stopwatch for runner
9) Morning alarm clock
10) Standard timer: Set a timer, then it counts down, then it plays a sound


## Part A. Solder your LCD panel

**Take a picture of your soldered panel and add it here!**

![Soldered LCD](/soldered_lcd.jpg)

## Part B. Writing to the LCD
 
**a. What voltage level do you need to power your display?**

5V

**b. What voltage level do you need to power the display backlight?**

3V
   
**c. What was one mistake you made when wiring up the display? How did you fix it?**

Nothing. It worked at first try.

**d. What line of code do you need to change to make it flash your name instead of "Hello World"?**

Replace `Hello World` with `hello, Zwee!` in the `setup()`:
<pre><code>
void setup() {
  // set up the LCD's number of columns and rows:
  lcd.begin(16, 2);
  // Print a message to the LCD.
  lcd.print("hello, Zwee!");
}
</code></pre>
 
**e. Include a copy of your Lowly Multimeter code in your lab write-up.**
<pre><code>
// include the library code:
#include &ltLiquidCrystal.h&gt

// initialize the library with the numbers of the interface pins
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);

int sensorPin = A0;    // select the input pin for the potentiometer
int sensorValue = 0;  // variable to store the value coming from the sensor

void setup() {
  // set up the LCD's number of columns and rows:
  lcd.begin(16, 2);
  // Print a message to the LCD.
  lcd.print("Sensor at Pin 0!");
}

void loop() {
  // read the value from the sensor:
  sensorValue = analogRead(sensorPin);

  // set the cursor to column 0, line 1
  // (note: line 1 is the second row, since counting begins with 0):
  lcd.setCursor(0, 1);
  // print the number of seconds since reset:
  lcd.print(sensorValue);
}
</code></pre>

## Part C. Using a time-based digital sensor

**Upload a video of your working rotary encoder here.**

[Rotary Encoder video](/rotary_encoder720.mov)

## Part D. Make your Arduino sing!

**a. How would you change the code to make the song play twice as fast?**

Change the value `1.30` to `0.65`. Though that will make it more difficult to distinguish notes.

<pre><code>
// to distinguish the notes, set a minimum time between them.
// the note's duration + 30% seems to work well:
int pauseBetweenNotes = noteDuration * 1.30;
delay(pauseBetweenNotes);
// stop the tone playing:
noTone(8);
</code></pre>
 
**b. What song is playing?**

Star Wars

## Part E. Make your own timer

**a. Make a short video showing how your timer works, and what happens when time is up!**

[Zwee Timer video](/zwee_timer720.mov)

**b. Post a link to the completed lab report your class hub GitHub repo.**
