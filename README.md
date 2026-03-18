# Interfacing-LCD-Using-8051
# NAME: GOKUL PRASAD H
# REG NO: 212224050011

## Aim:
To interface a 16x2 LCD with an 8051 microcontroller and display your name.

## Apparatus Required:
•	Laptop with Keil uVision software
•	Proteus Design Suite

## Algorithm:
1.Configure LCD in 4-bit mode.
2.Initialize LCD with commands.
3.Move the cursor direction.
4.Display ON
5.Set cursor position to the beginning (optional).
6.Send each character of the string "NAME" to the LCD one by one using data mode.
7.Continuously run the program to keep displaying the message.

## Program :
```
#include<reg51.h>
sbit rs-P1^0;
sbit rw=P1^1;
sbit en-P1^2;
void lcdcmd (unsigned char);
void lcddat (unsigned char);
void delay();
void main()
{
P2=0x00; 
while (1)
{
lcdcmd(0x38); // 5X7 matrix crystal
delay();
1cdcmd(0x01); 
delay();
lcdcmd(0x10); //cursor blinking
delay();
lcdcmd(0x0c); //display on
delay();
lcdcmd(0x81);
delay();
lcddat ('E');
delay();
lcddat ('M');
delay();
lcddat ('B'); I
delay();
lcddat('S');
delay();
lcddat('Y');
delay();
lcddat('S');
delay();
}
}
void lcdcmd (unsigned char val)
{
P2=val;
rs=0;
rw=0;
en-1;
delay();
en=0;
}
void lcddat (unsigned char val)
{
P2=val;
rs=1;
rw=0;
en=1;
delay();
en=0;
}
void delay()
{
unsigned int i;
for (i=0;i<12000; i++);
}
```


## Output :
<img width="1916" height="1199" alt="Screenshot 2026-03-18 192156" src="https://github.com/user-attachments/assets/bd98862c-2b05-44d5-84ba-0da64c82e973" />

<img width="1911" height="1187" alt="Screenshot 2026-03-18 192241" src="https://github.com/user-attachments/assets/cf0b20c2-6856-4610-bf23-a420346c3928" />

## Result :  
Thus interfacing LCD using 8051 microcontroller is executed successfully.


