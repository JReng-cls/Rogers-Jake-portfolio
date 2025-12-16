### Pomodoro Study Chair

For my Senior engineering capstone project I decided to build a pomodor study chair. The chair will be constructed of wood with a circuit in the arm of the chair that uses the pomodoro study method by keeping track of the study/break intervals. The chair will also encoporate a speaker to notify the user when they should switch from study to break or the other way around. 

## Side Design

I began by using a classroom chair as a reference design for my chair. I decided on creating two sides of the chair first anf then connecting across via mortison tenon joints. Using a classroom chair as a reference was benificial as they are smaller and would require less materials to replicate. I decided on making the chair seat at least 15 inches off of the ground. I wanted arms on the chair in order to integrate the electronics in them. 

On https://www.etsy.com I found a file for a bohemian chair and a tutorial on how to make it. However when I first imported the file via dxf on fusion360 the height was 324 inches tall. I re-inmported the deisign to millimeters in order to scale the size down. 

<img width="564" height="457" alt="image" src="https://github.com/user-attachments/assets/62fd3327-1945-4916-83ea-c89ae4fbf918" />

**Initial file imported in millimeters**

This chair was still not meeting the desired dimensions as it was only 24 inches tall and 45 inches wide. However the file did solve a cutting issue by breaking the side of the chair into pieces so that I would be able to arrange them on a smaller piece of wood.

By using the **Scale, move/copy, and line** tools on fusion360 I adjusted the height and width of the side to meet my desired dimensions

<img width="974" height="161" alt="image" src="https://github.com/user-attachments/assets/69da434a-a282-4584-b76b-f5be8a1510ec" />

**Side of chair broken into links that meet dimension requirements**

[Download DXF with Pieces to Side of Chair](https://raw.githubusercontent.com/JReng-cls/Rogers-Jake-portfolio/main/assets/css/Bohem_Tall_NS.dxf)

These links assemble to create a side frame 33 inches tall so that I can place the seat 17 inches off the ground

<img width="1145" height="1025" alt="image" src="https://github.com/user-attachments/assets/a64ad563-a1e5-416d-8690-bd452c456609" />

**Pieces cut out on cardboard and assembled**

When I cut this out using the shopbot cnc machine I will need two of these sides to create a full chair 

## Rasberry Pi Timer

For the electronics of my project I will be creating a circuit with a screen that displays a timer that keeps track of the pomodoro segments for the user. 

For my first circuit I used an LCD display with a Raspberry pi pico h

<img width="2237" height="1051" alt="image" src="https://github.com/user-attachments/assets/038efd5b-1630-4d1f-895c-85ce70603e59" />

**Starter circuit on Wokwi.com with raspberry pi pico and lcd display**

Using this circuit I was able to recreate the pinout on a breadboard and display a stopwatch timer on the LCD display

<img width="1356" height="702" alt="image" src="https://github.com/user-attachments/assets/976d1ede-43e2-4c7b-9944-30554ae62f7b" />

**Circuit with raspberry pi pico h chip connected to LCD display displaying a stopwatch tracking hours:minutes:seconds**

**Code used for LCD display:**

    #include <LiquidCrystal.h>

    LiquidCrystal lcd(12, 11, 10, 9, 8, 7);

    unsigned long previousMillis = 0;
    unsigned long elapsedSeconds = 0;

    void setup() {
    lcd.begin(16, 2);
    lcd.setCursor(0, 0);
    lcd.print("Stopwatch Running");
    }

    void loop() {
      unsigned long currentMillis = millis();

    // Update every 1000 ms (1 second)
    if (currentMillis - previousMillis >= 1000) {
    previousMillis = currentMillis;
    elapsedSeconds++;

     //Calculate hours, minutes, seconds
    int hours = elapsedSeconds / 3600;
    int minutes = (elapsedSeconds % 3600) / 60;
    int seconds = elapsedSeconds % 60;

    // Format time as HH:MM:SS
    char timeBuffer[9];
    sprintf(timeBuffer, "%02d:%02d:%02d", hours, minutes, seconds);

    // Display on second row
    lcd.setCursor(3, 1); // Centered-ish
    lcd.print(timeBuffer);
      }
    }

After seeing the display on the LCD I noticed that I couldn't see the timer very well from a view directly above the circuit. Mrs. Morrow suggested using a four pin OLED display 

<img width="2237" height="1056" alt="image" src="https://github.com/user-attachments/assets/13300775-9b3e-4177-8061-2ac480834bc6" />

**Wokwi circuit for Raspberry pi pico connected to OLED display**

<img width="1561" height="595" alt="image" src="https://github.com/user-attachments/assets/2f52f873-9379-45b5-94a4-8c86d74ac7a6" />

**Wokwi circuit recreated on breadboard. OLED displaying test text**

After creating this test circuit I used the same circuit and adjusted my code to add in a stopwatch that switches between study time and break time to recreate the pomodoro method. I also added in a buzzer speaker via another raspberry pi pin that buzzes everytime the segment switches from study to break or break to study

https://www.youtube.com/watch?v=VmAZWTmpMYU

[Working Raspberry Pi Pico h circuit with OLED display and buzzer speaking switching between study and break time]
## Daily Journal

- Day 1: On day one I spent my time searching for ergonomic chair designs to influence my own. I decided on creating a relatively smaller chair to support my budget. I decided on making the chair out of two different kinds of wood. One type that is harder or sturdier for the side/legs of the chair for support, and another type for the backrest and seat of the chair
- Day 2: I began measuring a chair in the lab to begin desiging my chair in fusion360. I used a classroom chair as a model in order to use less material as the chair is smaller than usual.
- Day 3: Measuring and designing
- Day 4: Measuring and designing
- Day 5: Test cut finished file on cardboard(Scaled down)
- Day 6: Re-designed file based off of test cut
- Day 7: Test cut new file on Cardboard(Scaled down)
- Day 8: Test cut file on wood(To scale)
- Day 9: Re-designed file based off of test cut and created adobe file to test on cardboard
- Day 10: Test cut on cardboard to see new size. Added fillets to the fusion file for smoother look. Created aspire file with new design.
- Day 11: Adjusted fusion360 file to be taller and less wide. It was 52 inches in length and only 26 inches tall. The ideal height would be 36 inches tall so that I can place the seat at least 15 inches off the ground
- Day 12: Began working on creating the timer circuit with a Raspberry pi pico h and a LCD display. Using arduino IDE and a template on Wokwi I was able to display a "hello world" message
- Day 13: Using AI I was able to write the code that displayed a timer on the LCD display with a message "Time Studying:"
- Day 14: I switched from an LCD display to an OLED display for a better view of the timer. I used a 4 pin OLED and kept the Raspberry Pi pico. I also switched to thonny IDE from Arduino IDE as it supports more raspberry pi pico h libraries
- Day 15: I was able to create code that ran a stopwatch with the same "Study time:" above the stopwatch
- Day 16: I added the pomodoro piece to my code by making the OLED display a Study time for 15 seconds then switch to break time for 5 seconds. These are not the typical time increments for the pomodoro study method so that I could test quicker
- Day 17: I added a buzzer speaker to my circuit with just a power and ground pin. I adjusted my code so that the speaker buzzes in between intervals. 
- Day 18: Broke chair file down into pieces so that I could arrange them to be efficient during cuts. I decided that when I cut these pieces out with wood on the shoptbot that I will use domino inserts to hold the pieces together.

