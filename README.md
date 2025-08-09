<img width="3188" height="1202" alt="frame (3)" src="https://github.com/user-attachments/assets/517ad8e9-ad22-457d-9538-a9e62d137cd7" />


# Abnormal Water Dispenser 🎯


## Basic Details
### Team Name: BIT JUNKIES


### Team Members
- Team Lead: JOE RAPHAEL JOSHY - CE VADAKARA
- Member 2: VIMAL DEV AS - CE VADAKARA

### Project Description
This is a playful and impractical water dispenser that only works when your mug is held upside down. Instead of filling your cup normally, it challenges common sense by activating the water flow only in the least useful position possible, making it a perfect example of a “useless” engineering concept. Built purely for humor and curiosity, it’s a fun reminder that not all inventions are meant to be practical.

### The Problem (that doesn't exist)
“People have had it far too easy filling cups the right way up. The world desperately needs a device that challenges basic logic and tests patience. By creating a water dispenser that only works when your mug is upside down, we solve the non-existent problem of making hydration inconvenient, messy, and mildly absurd.”

### The Solution (that nobody asked for)
“I’m solving it by building a high-tech, logic-defying dispenser that uses sensors to detect when your mug is upside down—only then will it graciously unleash a refreshing stream of water… straight onto the floor. It’s the perfect mix of engineering skill and complete uselessness.”

## Technical Details
### Technologies/Components Used
For Software:
- C++
- Arduino,servo motor ,harmonic sensor
- Servo.h – To control a servo motor that opens/closes the water valve.

LiquidCrystal.h (optional) – If you want an LCD display to show fun messages.

Wire.h – For I²C communication (used if your LCD or sensors require it).

Adafruit_Sensor.h – If you’re using certain orientation or tilt sensors.

Adafruit_MPU6050.h or MPU6050.h – For detecting if the mug is upside down using a gyroscope/accelerometer sensor.
- [Tools used]

For Hardware:
-Multimeter – For checking voltages and connections.

Screwdriver / Wire Cutter / Stripper – For preparing and assembling parts.

Soldering Kit – Only if you need permanent connections.


- [List specifications]
- [List tools required]

### Implementation
For Software:
# Installation
[commands]

# Run
#include <Servo.h>

Servo myServo;

// Ultrasonic Sensor Pins
const int trigPin = 9;
const int echoPin = 10;

// Servo positions
int servoHome = 90;   // Center position
int servoRotate = 0;  // 90° anticlockwise

void setup() {
  myServo.attach(3);   // Servo signal pin
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  
  myServo.write(servoHome); // Start at home position
  Serial.begin(9600);
}

void loop() {
  long duration;
  float distance;

  // Trigger the ultrasonic pulse
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);

  // Read echo pulse
  duration = pulseIn(echoPin, HIGH);

  // Convert to centimeters
  distance = duration * 0.034 / 2;

  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");

  if (distance > 0 && distance < 10) {
    // Object is closer than 10 cm
    myServo.write(servoRotate); 
  } 
  else if (distance >= 10) {
    // Object is farther than or equal to 10 cm
    myServo.write(servoHome);  
  }

  delay(100);
}


### Project Documentation
For Software:

# Screenshots (Add at least 3)
![Screenshot1](Add screenshot 1 here with proper name)
*Add caption explaining what this shows*

![Screenshot2](Add screenshot 2 here with proper name)
*Add caption explaining what this shows*

![Screenshot3](Add screenshot 3 here with proper name)
*Add caption explaining what this shows*

# Diagrams
![Workflow](Add your workflow/architecture diagram here)
*Add caption explaining your workflow*

For Hardware:

# Schematic & Circuit
![Circuit](Add your circuit diagram here)
*Add caption explaining connections*

![Schematic](Add your schematic diagram here)
*Add caption explaining the schematic*

# Build Photos
![Components](Add photo of your components here)
*List out all components shown*

![Build](Add photos of build process here)
*Explain the build steps*

![Final](Add photo of final product here)
*Explain the final build*

### Project Demo
# Video
[Add your demo video link here]
*Explain what the video demonstrates*

# Additional Demos
[Add any extra demo materials/links]

## Team Contributions
- [Name 1]: [Specific contributions]
- [Name 2]: [Specific contributions]
- [Name 3]: [Specific contributions]

---
Made with ❤️ at TinkerHub Useless Projects 

![Static Badge](https://img.shields.io/badge/TinkerHub-24?color=%23000000&link=https%3A%2F%2Fwww.tinkerhub.org%2F)
![Static Badge](https://img.shields.io/badge/UselessProjects--25-25?link=https%3A%2F%2Fwww.tinkerhub.org%2Fevents%2FQ2Q1TQKX6Q%2FUseless%2520Projects)



