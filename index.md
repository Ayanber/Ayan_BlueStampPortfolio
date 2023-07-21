# Air Quality Monitor
Many lives had been lost since several people are not aware that they have recieved low quality air. An sir quality monitor has an expensive cost on the market. To avoid paying a high price, people can make a cheap, portable, air quality monitor.  

You should comment out all portions of your portfolio that you have not completed yet, as well as any instructions:
```HTML 
<!--- This is an HTML comment in Markdown -->
<!--- Anything between these symbols will not render on the published site -->
```

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Ayan B. | Mission San Jose | Electrical Engineering | Incoming Freshmen |

**Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.**

![Headstone Image](logo.svg)
  
# Final Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/F7M7imOVGug" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For your final milestone, explain the outcome of your project. Key details to include are:
- What you've accomplished since your previous milestone
- What your biggest challenges and triumphs were at BSE
- A summary of key topics you learned about
- What you hope to learn in the future after everything you've learned at BSE



# Second Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/y3VAmNlER5Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
After I installed the MQ135, I wanted to install the DHT11 temperature/humidity sensor. However, the data of the DHT11 never appeared on the OLED. I realized that the limitted size of the OLED prevented the data from being displayed into the OLED. I switched the OLED to an LCD. Even though the LCD had more wirings, the data from the DHT11 was easily displayed. 
https://youtu.be/8SlSAUURaB8

For your second milestone, explain what you've worked on since your previous milestone. You can highlight:
- Technical details of what you've accomplished and how they contribute to the final goal
- What has been surprising about the project so far
- Previous challenges you faced that you overcame
- What needs to be completed before your final milestone 

# First Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/CaCazFBhYKs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
  When I started building the Air Quality Monitor, I needed to learn programming for Arduino IDE. I chose to start by installing the OLED. After I was built the circuit, I had difficulty placing the connection with the Arduino board and the OLED display. Since I have never used an OLED before, I searched for other strategies by experimenting with the circuit. After I installed the MQ135 senor, I realized that I require a 5v port for both items. However, I only had one port on the Arduino board. I learned that the edges of the Arduino board that had a + and - symbol can be used to transfer power through all the ports on the edges. I used the breadboard port edges to power the OLED display and the MQ135 sensor to be powered by 5v. 
https://youtu.be/_urRSI8ybJQ

# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. 
[Milestone 1.pdf](https://github.com/Ayanber/Ayan_BlueStampPortfolio/files/12072209/Milestone.1.pdf)





# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

**Final Milestone:**

**Second Milestone:**
#include "MQ135.h"
#include <dht11.h>
#include <LiquidCrystal.h>

// initialize the library with the numbers of the interface pins
LiquidCrystal lcd(7, 8, 9, 10, 11, 12);

const int ANALOGPIN = 0;
MQ135 gasSensor = MQ135(ANALOGPIN);
dht11 DHT11;
#define DHT11PIN 2
void setup() {
  Serial.begin(9600);  // put your setup code here, to run once:
// set up the LCD's number of columns and rows:
  lcd.begin(16, 2);
// Print a message to the LCD.
//  lcd.print("Hello, World!");
}

void loop() {  // put your main code here, to run repeatedly:
  float chk = DHT11.read(DHT11PIN);
  float gas = gasSensor.getPPM();
  lcd.setCursor(0, 0);
  lcd.print("T= ");
  lcd.print((int)DHT11.temperature);
  lcd.println("C  ");
  lcd.setCursor(8, 0);
  lcd.print("H= ");
  lcd.print((int)DHT11.humidity);
  lcd.println("%  ");
  lcd.setCursor(0, 1);
  lcd.print("Conc.= ");
  lcd.print(gas);
  lcd.println("ppm");

  Serial.print("Temperature [C] = ");
  Serial.println((int)DHT11.temperature);
  Serial.print("Humidity [%] = ");
  Serial.println((int)DHT11.humidity);
  Serial.print("Concentation [ppm] = ");
  Serial.println(gas);
  delay(10000);
}

**First Milestone:**
#include <Wire.h>
 
 
void setup()
{
  Wire.begin();
 
  Serial.begin(9600);
  while (!Serial);             // Leonardo: wait for serial monitor
  Serial.println("\nI2C Scanner");
}
 
 
void loop()
{
  byte error, address;
  int nDevices;
 
  Serial.println("Scanning...");
 
  nDevices = 0;
  for(address = 1; address < 127; address++ )
  {
    // The i2c_scanner uses the return value of
    // the Write.endTransmisstion to see if
    // a device did acknowledge to the address.
    Wire.beginTransmission(address);
    error = Wire.endTransmission();
 
    if (error == 0)
    {
      Serial.print("I2C device found at address 0x");
      if (address<16)
        Serial.print("0");
      Serial.print(address,HEX);
      Serial.println("  !");
 
      nDevices++;
    }
    else if (error==4)
    {
      Serial.print("Unknown error at address 0x");
      if (address<16)
        Serial.print("0");
      Serial.println(address,HEX);
    }    
  }
  if (nDevices == 0)
    Serial.println("No I2C devices found\n");
  else
    Serial.println("done\n");
 
  delay(5000);           // wait 5 seconds for next scan
}
const int gasSensor =0;
void setup(){
  Serial.begin(9600);      // sets the serial port to 9600
}
void loop(){
  float voltage;
  voltage = getVoltage(gasSensor);
  Serial.println(gasSensor.getPPM());
  Serial.println(voltage);
  delay(1000);
}
 
float getVoltage(int pin){
  return (analogRead(pin) * 0.004882814);
}
# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.mark downguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Breadboard | Power multiple sensor through wires. | $9.59 |  <a href="https://www.amazon.com/Qunqi-point-Experiment-Breadboard-5-5%C3%978-2%C3%970-85cm/dp/B0135IQ0ZC/ref=asc_df_B0135IQ0ZC/?tag=hyprod-20&linkCode=df0&hvadid=198091709182&hvpos=&hvnetw=g&hvrand=2250968856437206968&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9032046&hvtargid=pla-407203040794&psc=1/"> amazon </a>     |
| MQ135 | Measures the levels of gasses in the air. | $8.99 | <a href="https://www.amazon.com/Ximimark-Quality-Hazardous-Detection-Arduino/dp/B07L73VTTY/ref=sr_1_2?crid=1JQW6P88CP13S&keywords=MQ135&qid=1689645958&sprefix=mq135%2Caps%2C163&sr=8-2/"> amazon </a>|
| OLED | Displays results of data from MQ135 and DHT11 | $6.99 | <a href="https://www.amazon.com/UCTRONICS-SSD1306-Self-Luminous-Display-Raspberry/dp/B072Q2X2LL/ref=sr_1_5?crid=217K0GHNV4Y15&keywords=arduino+OLED&qid=1689645804&sprefix=arduino+ole%2Caps%2C167&sr=8-5"> amazon </a> |
| Elgoo Uno R3 Board | Transfers power through wire to LCD | $15.99 | <a href="https://www.amazon.com/ELEGOO-Board-ATmega328P-ATMEGA16U2-Compliant/dp/B01EWOE0UU/"> amazon </a> |
| Wires | Transfers power from an arduino board to multiple sensors | $7.99 | <a href="https://www.amazon.com/Solderless-Flexible-Breadboard-Jumper-Package/dp/B016KI622U/ref=sr_1_2_sspa?keywords=arduino+jumper+wires&qid=1689615065&sr=8-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1/"> amazon </a> |
| DHT11 | Measures the levels of temperature and humidity | $9.00 | <a href="https://www.amazon.com/Digital-Temperature-Relative-Humidity-Arduino/dp/B07868Z9LX/ref=sr_1_9?crid=29WH8QIDR2DMH&keywords=arduino+dht11&qid=1689615118&sprefix=arduino+dht11%2Caps%2C167&sr=8-9/"> amazon </a> |
| LCD   | Displays results of data from MQ135 and DHT11 | $9.99 | <a href="https://www.amazon.com/SunFounder-Serial-Module-Display-Arduino/dp/B019K5X53O/ref=sr_1_1_sspa?crid=3ODOT5YO1MWEL&keywords=arduino+lcd+display&qid=1689615363&sprefix=arduino+LCD%2Caps%2C159&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1/"> amazon </a> |
# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.
