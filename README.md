# excerecise_vent_control
An Arduino based wireless controller that includes a UI, humidity, temperature, and CO2 sensing and communicates to an in-wall relay to turn on a vent fan.

---
## Controller
Processor: ESP32
Built into a Wifi-BT-LoRa Wireless communications package with OLED, batter charger, and microusb plug.
3.3V
https://www.amazon.com/gp/product/B07HJ49VN8/ref=ppx_yo_dt_b_asin_title_o03_s04?ie=UTF8&psc=1

Display: 16X2 LCD
Simple 16x2 LCD for UI. I2C interface 
CAUTION: 5V! 
https://www.amazon.com/gp/product/B019K5X53O/ref=ppx_yo_dt_b_asin_title_o03_s03?ie=UTF8&psc=1

Temperature & Humidity Sensor: Adafruit (PID 3251) Si7021
Reasonably accurate I2C temperature and humidity sensor in breakout board.
3.3-5.0V
https://www.amazon.com/gp/product/B01M0BJ139/ref=ppx_yo_dt_b_asin_title_o03_s02?ie=UTF8&psc=1

CO2 Sensor: Adafruit (PID 3709) SGP30
Pretty nifty VOC and eCO2 sensor. This is by far the most challenging part to get to work right. It needs a 24hr baseline, often VOC levels will freate a false eCO2 level, and casing integration matters. Hoever this one will probably not need to be replaced in 6 months. 
1.7-5.0V
https://www.amazon.com/gp/product/B07L5YN11R/ref=ppx_yo_dt_b_asin_title_o03_s01?ie=UTF8&psc=1

Battery: 1.5Ah Lipoly
"Backup" battery

Enclosure: Adafruit White Enclosure for Arduino 
Seems like a reasonable design to start with. If I had a 3D printer I would put something together on my own.
https://www.amazon.com/gp/product/B00XW2NM6W/ref=ppx_yo_dt_b_asin_title_o02_s00?ie=UTF8&psc=1

## Wall Unit
Things that go into buildings or that interface with high voltage must be built with an abundance of cautiuon. No one wants to burn a building down or hurt someone. Whenever dealing with high voltge follow the appropriate codes. If ther are no existing codes for exactly what you are doing then build with best practices and act as though everything will fail at somepoint.

Processor: ESP32
Built into a Wifi-BT-LoRa Wireless communications package with OLED, batter charger, and microusb plug.
3.3V
https://www.amazon.com/gp/product/B07HJ49VN8/ref=ppx_yo_dt_b_asin_title_o03_s04?ie=UTF8&psc=1

Power Converter: MEAN WELL RS-15-5 
Smallest UL certified caged power converter from a brand I trust I could find. AC-DC converter to power the low voltage electronics.
110VAC -> 5VDC 15W
https://www.amazon.com/gp/product/B005T6UJBU/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1

Relay Board: 
This controls the actual fan power from the MCU. This is probably my least trusworthy part, not to say that it is a bad design, but if I were designing this board I'd be aiming for CAT III isolation along with some other protections. It does have a suppresison diode on the relay coil. Becasue it is a fan we are controlling it may need a supresison diode or capacitor.
Inout: 3.0-3.3V Output: 0-250V
https://www.amazon.com/gp/product/B01M0E6SQM/ref=ppx_yo_dt_b_asin_title_o03_s00?ie=UTF8&psc=1
