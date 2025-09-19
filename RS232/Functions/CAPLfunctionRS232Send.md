[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/RS232/Functions/CAPLfunctionRS232Send.md)

[CAPL Functions](../../CAPLfunctions.md) » [RS232](../CAPLfunctionsRS232Overview.md) » RS232Send

# RS232Send

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```
dword RS232Send( dword port, byte buffer[], dword number )
```

## Description

Sends a block of bytes to a serial port.

- The operation starts the sending of a block.
- The callback handler [RS232OnSend](CAPLfunctionRS232OnSend.md) will notify the node of completion.
- To get informed about errors occurring in later stages of the operation use [RS232OnError](CAPLfunctionRS232OnError.md). There are no automatic retrials in case of error.

## Parameters

- **port**: A number between 1 and 255 identifying a serial port.
- **buffer**: An array of bytes of which number will be sent.
- **number**: Number of bytes to send.

## Return Values

- **0**: error
  - The error occurs if
    - the serial port with the given number does not exist on the system
    - the port has not been opened
    - another non-blocking send operation has been used shortly before, leading to an error. Use the [RS232OnSend](CAPLfunctionRS232OnSend.md) callback handler to synchronize operations.
  - An error is only given if a problem is issued directly.
  - To get informed about errors occurring in later stages of the operation use [RS232OnError](CAPLfunctionRS232OnError.md).

- **1**: success
  - The operation may fail in later stages. Success means here, that the send operation could be started properly.

## Example

```c
char text[20] = "Hello World !";
byte buffer[20];
int i;
int length;
length = strlen(text) + 1;
for (i = 0; i < length; i++) buffer[i] = text[i];
if (1 == RS232Send(1, buffer, length))
    write("It works with port 1.");
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
