# ssd1306_rpi
ssd1306 Command Line Tool for Raspberry Pi / Orange Pi

128 X 64��OLED���R�}���h���C�����瑀��ł���c�[���ł��B  
SPI/I2C�ǂ���̃C���^�[�t�F�[�X�ɂ��Ή����Ă��܂��B  

���s���̈����̎w��͈ȉ��̒ʂ�ł��B  
+1   : 1�s�ڂɕ\�����镶���̎w��(�O���t�H���g�ŕ\���j  
+2   : 2�s�ڂɕ\�����镶���̎w��(�O���t�H���g�ŕ\���j  
+3   : 3�s�ڂɕ\�����镶���̎w��(�O���t�H���g�ŕ\���j  
+4   : 4�s�ڂɕ\�����镶���̎w��(�O���t�H���g�ŕ\���j  
+a   : 1�s�ڂɕ\�����镶���̎w��(�����t�H���g�ŕ\���j  
+b   : 2�s�ڂɕ\�����镶���̎w��(�����t�H���g�ŕ\���j  
+c   : 3�s�ڂɕ\�����镶���̎w��(�����t�H���g�ŕ\���j  
+d   : 4�s�ڂɕ\�����镶���̎w��(�����t�H���g�ŕ\���j  
-1   : 1�s�ڂ̕������폜  
-2   : 2�s�ڂ̕������폜  
-3   : 3�s�ڂ̕������폜  
-4   : 4�s�ڂ̕������폜  
+R n : n�s�ڂ𔽓]�ŕ\��  
-R n : n�s�ڂ̔��]������  
+U n : n�s�ڂ��A���_�[���C���t���ŕ\��  
-U n : n�s�ڂ̃A���_�[���C��������  
+L   : 1�s���X�N���[���A�b�v  
-L   : 1�s���X�N���[���_�E��  
P1 n : 1�s�ڂ̕\���J�n�ʒu��n�����ڂɐݒ�  
P2 n : 2�s�ڂ̕\���J�n�ʒu��n�����ڂɐݒ�  
P3 n : 3�s�ڂ̕\���J�n�ʒu��n�����ڂɐݒ�  
P4 n : 4�s�ڂ̕\���J�n�ʒu��n�����ڂɐݒ�  
c    : �S�Ă̕������폜  
s    : �\���𔽉f  

---

You can operate from command line.  
Command line parameters:  
+1 String : String for #1 line(with External Font)  
+2 String : String for #2 line(with External Font)  
+3 String : String for #3 line(with External Font)  
+4 String : String for #4 line(with External Font)  
+a String : String for #1 line(with Internal Font)  
+b String : String for #2 line(with Internal Font)  
+c String : String for #3 line(with Internal Font)  
+d String : String for #4 line(with Internal Font)  
-1 : delete #1 line  
-2 : delete #2 line  
-3 : delete #3 line  
-4 : delete #4 line  
+R n : Set inverse mode #n Line  
-R n : Unset inverse mode #n Line  
+U n : Set underline mode #n Line  
-U n : Unset underline mode #n Line  
+L   : Scroll Up 1Line  
-L   : Scroll Down 1Line  
P1 n : Set start colum n to line#1  
P2 n : Set start colum n to line#2  
P3 n : Set start colum n to line#3  
P4 n : Set start colum n to line#4  
c  : delete all string  
s  : show display  

You can use within script.  
#!/bin/bash  
./oled c  
./oled +1 "ABCDEFG"  
./oled +2 "abcdefg"  
./oled +3 "1234567"  
./oled +4 "Hello World!!"  
sudo ./oled s  

---

Wire connection for SPI

OLED---Raspberry  
Gnd----Gnd  
VCC----3.3V  
SCL----SCLK(Pin#23)  
SDA----MOSI(Pin#19)  
RST----GPIO2 *  
D/C----GPIO4 *  

(*)You can change any pin.  

---

Wire connection for I2C

OLED---Raspberry  
Gnd----Gnd  
VCC----3.3V  
SCK----SCL(Pin#5)  
SDA----SDA(Pin#3)  

---

Install for SPI  
git clone https://github.com/nopnop2002/ssd1306_rpi.git  
cd ssd1306_rpi/  
cc -o oled oled.c fontx.c -lwiringPi -DSPI  
sh ./test.sh  

---

Install for I2C  
git clone https://github.com/nopnop2002/ssd1306_rpi.git  
cd ssd1306_rpi/  
cc -o oled oled.c fontx.c -lwiringPi -DI2C  
sh ./test.sh  

---

![oled-1](https://cloud.githubusercontent.com/assets/6020549/24071131/782737a8-0c0e-11e7-9312-44ec00312f52.JPG)

![oled-2](https://cloud.githubusercontent.com/assets/6020549/24125314/71765782-0e0b-11e7-82b6-593d91cab8e4.jpg)

![oled-4](https://cloud.githubusercontent.com/assets/6020549/24076582/e037998c-0c77-11e7-9e48-525e27c478a3.JPG)

Line1-2 : External Font  
Line3-4 : Internal Font  


![oled-5](https://cloud.githubusercontent.com/assets/6020549/24076875/c9c2c700-0c7f-11e7-8c0d-e000dcdff05e.JPG)


---

Set start colum  

![oled-6](https://cloud.githubusercontent.com/assets/6020549/24125179/b3b09bfe-0e0a-11e7-83bc-9dbd7b26db18.JPG)


![oled-7](https://cloud.githubusercontent.com/assets/6020549/24125192/d2c40328-0e0a-11e7-8a6a-884c0600059e.JPG)
