
######HDC100X_Arduino_Library
This is an Arduino library for the HDC1008/HDC1000 I²C temperature and humidity sensor.

This library was written for the Texas Instruments HDC100X temperature and humidity sensor.
It has been tested for the HDC1000 and the HDC1008.
Code is on GitHub: https://github.com/RFgermany/HDC100X-Arduino-Library.git
Please buy the HDC1008 breakout board at: https://www.tindie.com/stores/RFgermany
This library is made by Florian Roesner.
Released under GNU GPL v2.0 license.
More info in the .cpp file

#####List of funktions:
######class HDC100X
######{
######public:
######HDC100X();
######HDC100X(uint8_t address);
######HDC100X(bool addr0, bool addr1);
######uint8_t begin(uint8_t mode, uint8_t tempRes, uint8_t humiRes, bool heaterState);
######uint8_t begin(uint8_t mode, uint8_t resulution, bool heaterState);
######void setAddr(uint8_t address);
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
###}


###List of defines:

######HDC100X_DEFAULT_ADDR		0x40

######HDC100X_TEMP_REG			0x00
######HDC100X_HUMI_REG			0x01
######HDC100X_CONFIG_REG			0x02
######HDC100X_ID1_REG				0xFB
######HDC100X_ID2_REG				0xFC
######HDC100X_ID3_REG				0xFD
######HDC100X_RST					0x80
######HDC100X_TEMP_HUMI			0x16
######HDC100X_HUMI				1
######HDC100X_TEMP				0
######HDC100X_14BIT				0x00
######HDC100X_11BIT				0x01
######HDC100X_8BIT				0x02
######DISABLE						0
######ENABLE						1
