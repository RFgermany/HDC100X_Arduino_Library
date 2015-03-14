
######HDC100X_Arduino_Library
This is an Arduino library for the HDC1008/HDC1000 I²C temperature and humidity sensor.

This library was written for the Texas Instruments HDC100X temperature and humidity sensor.
It has been tested for the HDC1000 and the HDC1008.
Code is on GitHub: https://github.com/RFgermany/HDC100X-Arduino-Library.git
Please buy the HDC1008 breakout board at: https://www.tindie.com/stores/RFgermany
This library is made by Florian Roesner.
Released under GNU GPL v2.0 license.

#List of funktions:
##class HDC100X
##{
####public:
######HDC100X();
// set the slave address
######HDC100X(uint8_t address);
// set the two bits the way you set the address jumpers this will generate and sets the slave address
######HDC100X(bool addr0, bool addr1);

/* sets the mode and resolution and the state of the heater element. care must be taken, because it will change the temperature reading
** in:
** mode: HDC100X_TEMP_HUMI
** tempRes: HDC100X_11BIT/HDC100X_14BIT
** humiRes: HDC100X_8BIT/HDC100X_11BIT/HDC100X_14BIT
** heaterState: ENABLE/DISABLE
** out:
*/ high byte of the configuration register

######uint8_t begin(uint8_t mode, uint8_t tempRes, uint8_t humiRes, bool heaterState);
/* sets the mode, resolution and heaterState. Care must be taken, because it will change the temperature reading
** in:
** mode: HDC100X_TEMP/HDC100X_HUMI
** resolution: HDC100X_8BIT/HDC100X_11BIT(both)
HDC100X_14BIT(both)
** heaterState: ENABLE/DISABLE
** out:
** high byte of the configuration register
*/
######uint8_t begin(uint8_t mode, uint8_t resulution, bool heaterState);
/* sets the slave address
** in:
** address: slave address byte
** out:
** none
*/
######void setAddr(uint8_t address);
/* sets the slave address
** in:
** addr0: true/false
** addr1: true/false
** out:
** none
*/
######void setAddr(bool addr0, bool addr1);
######void setDrPin(int8_t pin);
######uint8_t setMode(uint8_t mode, uint8_t tempRes, uint8_t humiRes);
######uint8_t setMode(uint8_t mode, uint8_t resolution);
######uint8_t setHeater(bool state);
######bool battLow(void);
######float getTemp(void);
######float getHumi(void);
######uint16_t getRawTemp(void);
######uint16_t getRawHumi(void);
######uint8_t getConfigReg(void);
######uint16_t read2Byte(uint8_t reg);
######uint8_t writeConfigData(uint8_t config);
####private:
######uint8_t ownAddr;
######uint8_t dataReadyPin;
######uint8_t HDCmode;
######void setRegister(uint8_t reg);
##}