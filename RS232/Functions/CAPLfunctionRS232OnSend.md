# RS232OnSend

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
RS232OnSend( dword port, byte buffer[], dword number );
```

## Description

Callback handler for completion of send operation to a serial port.

**Note**

- Will be called only at the node which issued the send operation.
- The handler will only be called for success. For errors [RS232OnError](CAPLfunctionRS232OnError.md) will be called.

## Parameters

- **port**: A number between 1 and 255 identifying a serial port.
- **buffer**: The buffer given to the send call.
- **number**: The number of bytes which have been sent.

## Return Values

- **0**: error
  - The error occurs if no send operation will be used.
- **1**: success

## Example

```c
char text[20] = "Hello World !";
byte block[20];
int i;
int length;
length=strlen(text)+1;
for (i=0;i<length;i++) block[i]=text[i];

if ( 0!=RS232Send(1,block,length) )
    write("Written block of bytes to port 1.");
...
// at node which issued the send request
RS232OnSend(dword port, byte buffer[], dword number)
{
    // send completed now, it may time to issue the next send
    // buffer==block, number==length
}
```
