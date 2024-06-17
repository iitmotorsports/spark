# CAN Bus Communications

## Description

CAN(Controller Area Network) is a bus used most commonly in vehicles designed to allow microcontrollers and devices to communicate with each other without a host computer. All microcontrollers and devices all connect to a CAN transceiver then every transceiver is connected to the a twisted pair of wires. All communicaation happens on the two wires and you can have as many devices as you want. CAN allows you to do a form of filtering where every message has a address assigned before sending that only a device or microcontroller that has the same "mask" will read it. It is highly recommended that you make it asynchronous/inturupt based to allow faster reaction/transfer of info.

![](/assets/energetics/concepts/can_bus_frame.svg)

Example: Communication of logging messages or state data from one microcontroller to another microcontroller.

## Hardware

In this example we will be using two [Teensy 3.6](https://www.pjrc.com/store/teensy36.html). These are nice because they have specific pins that are capable of working with the transceiver without the library having to do much. Two CAN transceivers are also needed a good one is [SN65HVD230](https://www.waveshare.com/sn65hvd230-can-board.htm). 

![](/assets/energetics/concepts/teensy36.jpg)

![](/assets/energetics/concepts/waveform.jpg)

## Library

The library that was and will be used in this example is [FlexCan](https://github.com/pawelsky/FlexCAN_Library). This one is designed for Teensy 3.1 to 3.6.

## Code

There are two seperate examples here where one will be a sender and the other will be a reciever

<details open>
	<summary>Sender</summary>
``` c++
#include <Arduino.h>
#include <FlexCAN.h>

bool pin1 = false;
bool pin2 = false;
bool pin3 = false;
bool pin4 = false;
bool pin5 = false;

FlexCAN CAN0;
CAN_message_t msg;

void oneBytePackage() {
    msg.len = 1;
    uint8_t package = 00000000;
    uint8_t add = 00000001;
    if(pin1){
        package = package | add;
    }
    package = package << 1;
    if(pin2){
        package = package | add;
    }
    package = package << 1;
    if(pin3){
        package = package | add;
    }
    package = package << 1;
    if(pin4){
        package = package | add;
    }
    package = package << 1;
    if(pin5){
        package = package | add;
    }
    msg.buf[0] = package;
    Serial.println(msg.buf[0]);
}

void setup() {
// write your initialization code here
    CAN0 = FlexCAN(125000, 0, 0, 0);
    pinMode(33, INPUT_PULLDOWN);
    pinMode(34, INPUT_PULLDOWN);
    pinMode(35, INPUT_PULLDOWN);
    pinMode(36, INPUT_PULLDOWN);
    pinMode(37, INPUT_PULLDOWN);

    CAN0.begin();

    Serial.print("hi");
}

void loop() {
    pin1 = digitalRead(33);
    pin2 = digitalRead(34);
    pin3 = digitalRead(35);
    pin4 = digitalRead(36);
    pin5 = digitalRead(37);

    oneBytePackage();
    CAN0.write(msg);
}
```
</details>

The sender in this example is reading a couple switches then oneBytePackage() does bitwise operations to create a 5 bit package then puts it in the allowed 8 bit buffer. Also the msg.len is important to be equal to the amount of buffer you are going to use since the reading side will use it to decide how many buffers it has to read. it is also possible to just throw a number in their however keep in mind that a byte can only hold a number between 0 and 256 unsigned. Lastly also keep in mind that this is not do with any async/inturupt.

<details open>
	<summary>Reciever</summary>
``` c++
#include <Arduino.h>
#include <FlexCAN.h>

FlexCAN CAN0;
CAN_message_t msg;

bool pin1 = false;
bool pin2 = false;
bool pin3 = false;
bool pin4 = false;
bool pin5 = false;

void oneByteDecoder(){
    uint8_t package = msg.buf[0];
    uint8_t test = 00000001;
    if ((package & test) == 1){
        pin5 = true;
    } else {
        pin5 = false;
    }
    package = package >> 1;
    if ((package & test) == 1){
        pin4 = true;
    } else {
        pin4 = false;
    }
    package = package >> 1;
    if ((package & test) == 1){
        pin3 = true;
    } else {
        pin3 = false;
    }
    package = package >> 1;
    if ((package & test) == 1){
        pin2 = true;
    } else {
        pin2 = false;
    }
    package = package >> 1;
    if ((package & test) == 1){
        pin1 = true;
    } else {
        pin1 = false;
    }
}

void pinChange() {
    digitalWrite(24,pin1);
    digitalWrite(12,pin2);
    digitalWrite(10,pin3);
    digitalWrite(8,pin4);
    digitalWrite(6,pin5);
}

void setup() {
    FlexCAN(125000, 0, 0, 0);
    pinMode(6, OUTPUT);
    pinMode(8, OUTPUT);
    pinMode(10, OUTPUT);
    pinMode(12, OUTPUT);
    pinMode(24, OUTPUT);
    digitalWrite(6, LOW);   //bit line position 5
    digitalWrite(8, LOW);   //bit line position 4
    digitalWrite(10, LOW);  //bit line position 3
    digitalWrite(12, LOW);  //bit line position 2
    digitalWrite(24, LOW);  //bit line position 1

    CAN0.begin();
}

void loop() {
    CAN0.read(msg);
    oneByteDecoder();
    pinChange();
}
```
</details>

The reader first tries to read from CAN and if it does then will save it to the msg the decoder uses bitwise operators to convert the byte of data we recieved and then turns it into boolean values that then represent the state of the switches the sender read and sent.