# I2C controller

This is a library forked from [@TeraHz](https://github.com/TeraHz) on github.

I will be using this to connect to the [ADAfruit raspberry PI DC Stepper](https://learn.adafruit.com/adafruit-dc-and-stepper-motor-hat-for-raspberry-pi/using-stepper-motors) module.



## Instruction for use

```c++

//use include headers
#include "I2C.h"

int main(){    
    
    int address {0x60};
    //Normally 1 for RaspberryPI 3b
    // just check using i2cdetect
    I2C connection = I2C(1,address);

    //depending on the spec you can either read from 0x00 or somewhere else.
    //
    uint8_t data{0};
    data = I2C.read_byte(0x00);
    
    //write att address 0x40 with commands 0x00
    uint8_t reg{0x40};
    uint8_t command{0x00};
    if(I2C.write_byte(reg,command) <0){
     printf("Error writing at address 0x%x",address);
    exit(-1);
    }       


}


```

