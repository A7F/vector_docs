[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/RS232/Functions/CAPLfunctionRS232OnReceive.md)

[CAPL Functions](../../CAPLfunctions.md) » [RS232](../CAPLfunctionsRS232Overview.md) » RS232OnReceive

# RS232OnReceive

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

`RS232OnReceive( dword port, byte buffer[], dword number );`

## Description

Callback handler for reception of data at a serial port.

**Note**
- Will be called only at the nodes which issued a [RS232Receive](CAPLfunctionRS232Receive.md) operation for the given port.
- The handler will only be called for success. For errors [RS232OnError](CAPLfunctionRS232OnError.md) will be called.
- The buffer may be much larger than number. For very slow connections, the handler may get called for few bytes. At least one byte is given.
- It is possible to listen to one and the same port at several nodes. All nodes will be called with the same data.

## Parameters

- **port**: A number between 1 and 255 identifying a serial port.
- **buffer**: The buffer given to the start [receive call](CAPLfunctionRS232Receive.md).
- **number**: The number of bytes which have been received.

  **Note**
  - The number of received bytes will vary strongly with the speed of the connection.

## Return Values

- **0**: error
  - The error occurs if no start receive operation has been.
- **1**: success

## Example

```c
// at sender node
char text[20] = "Hello World !";
byte block[20];
int i;
int length;
length=strlen(text)+1;
for (i=0;i<length;i++) block[i]=text[i];

if ( 0!=RS232Send(1,block,length) )
    write("Written block of bytes to port 1.");
...
// at receiver node (here 2)
byte mybuffer[100];
int mysize = 100;
RS232Receive(2,mybuffer,mysize);
...
// at node which issued the receive request
RS232OnReceive(dword port, byte buffer[], dword number)
{
    // port==2 here
    // buffer==mybuffer, number<=mysize
    // buffer contains some parts of block
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
