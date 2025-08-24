# Bitmap_Examples
<h3> <b> A predefined repository of bitmap examples for a 128x64 pixel display using the ESP8266 with the SSD1306 module. </b> </h3> <br />
<div align="center"><img src="https://c.tenor.com/1qupgAaVsJgAAAAd/tenor.gif" loop=infinite /></div>
<br />

### Make use of this [link](https://lastminuteengineers.com/oled-display-esp8266-tutorial/#esp8266-example-code-3-dispaying-bitmap) for your code base or copy this

```c
#include <SPI.h>
#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>

#define SCREEN_WIDTH 128  // OLED display width, in pixels
#define SCREEN_HEIGHT 64  // OLED display height, in pixels

// Declaration for SSD1306 display connected using I2C
#define OLED_RESET -1  // Reset pin
#define SCREEN_ADDRESS 0x3C
Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, &Wire, OLED_RESET);

...
//bitmap code here
...

const int epd_bitmap_allArray_LEN = 1;
const unsigned char* epd_bitmap_allArray[1] = {
	<<module name here>>
};


void setup() {
  Serial.begin(9600);

  // initialize the OLED object
  if (!display.begin(SSD1306_SWITCHCAPVCC, SCREEN_ADDRESS)) {
    Serial.println(F("SSD1306 allocation failed"));
    for (;;)
      ;
  }

  // Clear the buffer.
  display.clearDisplay();
  display.drawBitmap(32, 0, <<module name here>> , 64, 64, WHITE);
  display.display();

  // Invert Display
  //display.invertDisplay(1);
}

void loop() {
}
```
<br>

here module name can be find from `copy from` directed folder.

<br>

Example: image2.ino

```arduino
const unsigned char epd_bitmap_image2 [] PROGMEM = {
	0xff, 0xff, 0xff,
.....
.....
}
```

`epd_bitmap_image2` is the module name so copy it and append it in ``<<module name here>> ``, one right below bitmap code(that .ino file you copied) and another on second line of  `Clear the buffer` comment.

<br />

## Images and links :)

 ![k](https://github.com/user-attachments/assets/1cfd0cf5-580b-4212-acb2-9bffcfea5248)  
 
 > image1 [source: r/pixelart](https://www.reddit.com/r/PixelArt/comments/fnamaf/7_colors_used_128x64_pxls_hope_you_like_it/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button)

[copy from](examples/image1.ino)

<br />

![image2](https://github.com/user-attachments/assets/b669de43-ab6e-427b-a29d-c29da23d3a31)

> image2 [source: Deviantart](https://www.deviantart.com/suchanames/art/Skull-in-pixel-art-64X64-905035597)

[copy from](examples/image2.ino)

<br />

![image3](https://github.com/user-attachments/assets/64e2f21b-db22-442b-948b-a28b307892ee)

> image3 [source: r/pixelart](https://www.reddit.com/r/PixelArt/comments/1ad48b4/nidoking_64x64/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button)

[copy from](examples/image3.ino)

<br />

* A awesome skeleton gif [repository](https://github.com/sandhan26/Skeletor-animation-arduino.git), you can make use of [this](https://github.com/sandhan26/Skeletor-animation-arduino/tree/master/skeletor_v1) file for learning.
