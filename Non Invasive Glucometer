* IoT Non invasive blood glucose level monitor
 */
// SCL D1
// SDA D2

#include <Wire.h>
#include "MAX30105.h"
#include "heartRate.h"
MAX30105 particleSensor;

#include <LiquidCrystal_I2C.h>
LiquidCrystal_I2C lcd(0x27,16,2);

const byte RATE_SIZE = 4; //Increase this for more averaging. 4 is good.
byte rates[RATE_SIZE]; //Array of heart rates
byte rateSpot = 0;
long lastBeat = 0; //Time at which the last beat occurred
float beatsPerMinute;
int beatAvg;
float temperature;
int FallState= 0;
int BPM = 0;


void setup()
{ 
  Serial.begin(9600);
  Serial.println("Initializing...");
  lcd.begin();                      
  lcd.backlight();
  if (!particleSensor.begin(Wire, I2C_SPEED_FAST)) //Use default I2C port, 400kHz speed
  {
    Serial.println("MAX30105 was not found. Please check wiring/power. ");
    lcd.setCursor(0,0);
    lcd.print("Not Found");
    while (1);
  }
  Serial.println("Place your index finger on the sensor with steady pressure.");
  particleSensor.setup(); //Configure sensor with default settings
  particleSensor.setPulseAmplitudeRed(0x0A); //Turn Red LED to low to indicate sensor is running
  particleSensor.setPulseAmplitudeGreen(0); //Turn off Green LED
  }

void loop()
{
  long irValue = particleSensor.getIR();
  if (checkForBeat(irValue) == true)
  {
    //We sensed a beat!
    long delta = millis() - lastBeat;
    lastBeat = millis();
    beatsPerMinute = 60 / (delta / 1000.0);
    if (beatsPerMinute < 255 && beatsPerMinute > 20)
    {
      rates[rateSpot++] = (byte)beatsPerMinute; //Store this reading in the array
      rateSpot %= RATE_SIZE; //Wrap variable
      //Take average of readings
      beatAvg = 0;
      for (byte x = 0 ; x < RATE_SIZE ; x++)
        beatAvg += rates[x];
      beatAvg /= RATE_SIZE;
    }
  }
  temperature = particleSensor.readTemperature();
  Serial.print("IR=");
  Serial.println(irValue);
  //Serial.print(", BPM=");
  //Serial.print(beatsPerMinute);
  //Serial.print(", Avg BPM=");
  //Serial.print(beatAvg);
  //Serial.print(", Temperature=");
  //Serial.print(temperature);
  if(irValue < 70000)
  {
    Serial.print("IR = ");
    Serial.print(0);
    Serial.print(" Temperature = ");
    Serial.print(0);
    lcd.setCursor(0,0);
    lcd.print("  Place Finger   ");
    lcd.setCursor(0,1);
    lcd.print("                ");
    
  }
  else
  {
    delay(1000);
    Serial.print("IR = ");
    Serial.print(irValue);
    //Serial.print(" Temperature = ");
    //Serial.print(temperature);
    lcd.clear();
    lcd.setCursor(0,0);
    lcd.print("Reading Value");
    delay(800);
    lcd.setCursor(0,0);
    lcd.print("Reading Value.");
    delay(800);
    lcd.setCursor(0,0);
    lcd.print("Reading Value..");
    delay(800);
    lcd.setCursor(0,0);
    lcd.print("Reading Value...");
    delay(1000);
    lcd.clear();
    irValue = map(irValue, 70000, 92000, 70, 110);
    lcd.setCursor(0,0);
    lcd.print(" Glucose Level ");
    lcd.setCursor(4,1);
    lcd.print(irValue);
    lcd.setCursor(8,1);
    lcd.print("mg/dL");
    delay(2000);
    lcd.clear();
    lcd.setCursor(0,0);
    lcd.print("   Take Finger   ");
    delay(4000);
    lcd.clear();  
  }
  /*if (irValue < 50000)
  Serial.print(" No finger?");
  Serial.println();*/
}
