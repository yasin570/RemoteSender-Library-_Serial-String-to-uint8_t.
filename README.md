# RemoteSender
Dividing a comma-separated string into pieces, converting these pieces into hexadecimal numbers, and transmitting these hexadecimal numbers through the serial port.  String to uint8_t.   String ("A1,B1") to uint8_t.



How to use ?

Download RemoteSenderESP8266.zip and add it to the library.

#include <SoftwareSerial.h>
#include "RemoteSenderESP8266.h"

SoftwareSerial mySoftwareSerial(12, 14); // RX, TX
RemoteSenderESP8266 remoteSender(mySoftwareSerial);

void setup() {
  Serial.begin(9600);
  mySoftwareSerial.begin(9600);
}

void loop() {
  String dataToSend = "0xFF,0xAA";
  
  remoteSender.send(dataToSend);

  delay(1000);
}

