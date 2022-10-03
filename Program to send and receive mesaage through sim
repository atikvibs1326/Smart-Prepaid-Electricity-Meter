#include <SoftwareSerial.h>
SoftwareSerial mySerial(2, 3);  // 2 = Rx 3 = Tx

void setup()
{
  mySerial.begin(9600);   // Setting the baud rate of Serial2 Module  
  Serial.begin(9600);    // Setting the baud rate of Serial Monitor (Arduino)
 			 //delay(100);
}


void loop()
{
  if (Serial.available()>0) 	// arduino serial port
   switch(Serial.read())
  {
    case 's':
      MessageSendKaro();
      break;
    case 'r':
      MessageAayaHai();
      break;
  }

 if (mySerial.available()>0) 				// Serial2 serial port
   Serial.write(mySerial.read());
}

 void MessageSendKaro()
{
  mySerial.println("AT+CMGF=1");    		//Sets the Serial2 Module in Text Mode
  delay(1000);                                 		  	  // Delay of 1000 milli seconds or 1 second
  mySerial.println("AT+CMGS=\"+917558280906\"\r");   // Replace x with mobile number
  delay(1000);
  mySerial.println("hi....hello.....!!!!");                  // The SMS text you want to send
  delay(100);
  mySerial.println((char)26);			// ASCII code of CTRL+Z
  delay(1000);
}


 void MessageAayaHai()
{
  mySerial.println("AT+CNMI=2,2,0,0,0"); 		// AT Command to receive a live SMS
  delay(1000);
 }
