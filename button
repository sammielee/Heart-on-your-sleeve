#include <Adafruit_NeoPixel.h>
const int SWITCH_PIN = 6;
const int LED_PIN = 12;

const int DATA_PIN = 12;
const int PIXEL_NUM = 1;      // number of pixels

int counter = 0; //counter for LED colors

const int BRIGHTNESS = 200;   // 0-255
const int WAIT = 50;          // delay transitioning colors

Adafruit_NeoPixel strip = Adafruit_NeoPixel(PIXEL_NUM, DATA_PIN, NEO_GRB + NEO_KHZ800);
const uint32_t BLUE = strip.Color(0, 0, 255);
int last_pin_state;
 
void setup() {
  pinMode(SWITCH_PIN, INPUT);
  digitalWrite(SWITCH_PIN, HIGH);
  pinMode(LED_PIN, OUTPUT);

  pinMode(DATA_PIN, INPUT);
  digitalWrite(DATA_PIN, HIGH);
  strip.begin();
  strip.setBrightness(BRIGHTNESS);
}
 
void loop() {
  int pin_state = digitalRead(SWITCH_PIN);
  if (pin_state != last_pin_state) {
    delay(WAIT);
    if(counter == 0){ //Red
    strip.setPixelColor(0, 255, 0, 0);
    //strip.show();
    ++counter;
    }
    else if(counter == 1){  //Yellow
    strip.setPixelColor(0, 195, 233, 0);
    //strip.show();
    ++counter;
    }
    else if(counter == 2) //Green
    {
    strip.setPixelColor(0, 0, 255, 0);
    //strip.show();
    ++counter;
    }
    else if(counter == 3) //Blue
    {
    strip.setPixelColor(0, 0, 0, 255);
    //strip.show();
    ++counter;
    }
    else if(counter == 4) //Purple
    {
    strip.setPixelColor(0, 190, 0, 255);
    ++counter;
    }
    else if(counter == 5) //Turn off
    {
    strip.setPixelColor(0, 0, 0, 0);
    counter = 0;
    }
    strip.show();
    int led_state = (pin_state == LOW) ? HIGH : LOW;
    last_pin_state = pin_state;
  }
}
