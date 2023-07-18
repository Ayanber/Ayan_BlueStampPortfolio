# Air Monitor Control
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
Hello, my name is Ayan. I have updated my project. In this video, I will be explaining my second milestone. For my project, the Air Quality Monitor, I previously used an OLED to display the readings of temperature, humidity, and air quality. However, since the OLED size was limited, it wasn’t able to  I switched the OLED with an LCD. The LCD was able to display the data from the sensors in better quality. The LCD is connected by multiple wires of digital pins. The LCD is further connected by a potentiometer. Three wires are connected to the potentiometer to power it. When the potentiometer turns, the brightness of the LCD monitor changes. The MQ135 and DHT11 sensors are now connected to the LCD. The LCD display three sets of data. Temperature, humidity, and concentration. The code used ppm which changes the data on the display the results detected by the MQ135 and DHT11. Thank you for listening to my Milestone 2 video. 



For your second milestone, explain what you've worked on since your previous milestone. You can highlight:
- Technical details of what you've accomplished and how they contribute to the final goal
- What has been surprising about the project so far
- Previous challenges you faced that you overcame
- What needs to be completed before your final milestone 

# First Milestone

**Don't forget to replace the text below with the embedding for your milestone video. Go to Youtube, click Share -> Embed, and copy and paste the code to replace what's below.**

<iframe width="560" height="315" src="https://www.youtube.com/embed/CaCazFBhYKs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
  Before I started building the Air Quality Monitor, I primarily needed to learn programming for Arduino IDE. When I was buikding the circuit, I had difficulty placing the connection with the Arduino board and the OLED display. Since I have never used an OLED before, I searched for other strategies by experimenting with the circuit. After I installed the MQ135 senor, I realized that I require a 5v port for both items. However, I only had one port on the Arduino board. I learned that the edges of the Arduino board that had a + and - symbol can be used to transfer power all the ports on the edges. I used the breadboard port edges to power the OLED display and the MQ135 sensor to be powered by 5v. 

# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. 
[Milestone 1.pdf](https://github.com/Ayanber/Ayan_BlueStampPortfolio/files/12072209/Milestone.1.pdf)





# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

```c++
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  Serial.println("Hello World!");
}

void loop() {
  // put your main code here, to run repeatedly:

}
```

# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.mark downguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| Breadboard | Power multiple sensor through wires. | $9.59 |Amazon |
| MQ135 | Measures the levels of gasses in the air. | $8.99 | Amazon|
| OLED | Displays results of data from MQ135 and DHT11 | $ | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/"> Link </a> |
| Elgoo Uno R3 Board |  | $15.99 | https://www.amazon.com/ELEGOO-Board-ATmega328P-ATMEGA16U2-Compliant/dp/B01EWOE0UU/ref=sr_1_3?crid=2CKV6W384Y9N7&keywords=arduino+elegoo+uno+r3+board&qid=1689615189&sprefix=arduino+elgoo+uno+r3+boar%2Caps%2C150&sr=8-3 |
| Wires | Transfers power from an arduino board to multiple sensors | $7.99 | https://www.amazon.com/Solderless-Flexible-Breadboard-Jumper-Package/dp/B016KI622U/ref=sr_1_2_sspa?keywords=arduino+jumper+wires&qid=1689615065&sr=8-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1 |
| DHT11 | Measures the levels of temperature and humidity | $9.00 | https://www.amazon.com/Digital-Temperature-Relative-Humidity-Arduino/dp/B07868Z9LX/ref=sr_1_9?crid=29WH8QIDR2DMH&keywords=arduino+dht11&qid=1689615118&sprefix=arduino+dht11%2Caps%2C167&sr=8-9 |
| LCD   | Displays results of data from MQ135 and DHT11 | $9.99 | https://www.amazon.com/SunFounder-Serial-Module-Display-Arduino/dp/B019K5X53O/ref=sr_1_1_sspa?crid=3ODOT5YO1MWEL&keywords=arduino+lcd+display&qid=1689615363&sprefix=arduino+LCD%2Caps%2C159&sr=8-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&psc=1 |
# Other Resources/Examples
One of the best parts about Github is that you can view how other people set up their own work. Here are some past BSE portfolios that are awesome examples. You can view how they set up their portfolio, and you can view their index.md files to understand how they implemented different portfolio components.
- [Example 1](https://trashytuber.github.io/YimingJiaBlueStamp/)
- [Example 2](https://sviatil0.github.io/Sviatoslav_BSE/)
- [Example 3](https://arneshkumar.github.io/arneshbluestamp/)

To watch the BSE tutorial on how to create a portfolio, click here.
