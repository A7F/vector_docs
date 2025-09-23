# RS232Receive

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
dword RS232Receive( dword port, byte buffer[], dword size );
```

## Description

Receive blocks of bytes from a serial port.

- The operation works continuous if issued once.
- If any data has been received, the node will be notified by the callback handler [RS232OnReceive](CAPLfunctionRS232OnReceive.md).
- If another receive operation will be given, the result buffer will change to that one given by the last receive operation.
- To get informed about errors occurring in later stages of the operation use [RS232OnError](CAPLfunctionRS232OnError.md). Retrials to receive will be started continuously but you won’t be notified if an error happens again.

## Parameters

- **port**: A number between 1 and 255 identifying a serial port.
- **buffer**: An array of bytes.
- **size**: Maximum number of bytes which can be received.

## Return Values

- **0**: error
  - The error occurs if:
    - the serial port with the given number does not exist on the system
    - the port has not been opened
  - An error is only given if a problem is issued directly by the system.
  - To get informed about errors occurring in later stages of the operation use [RS232OnError](CAPLfunctionRS232OnError.md).

- **1**: success
  - Success means here, that the receive operation could be started properly.

## Example

```plaintext
byte mybuffer[20];
int mysize=20;
if ( 1==RS232Receive(1,mybuffer,mysize) )
  write("It works with port 1.");
...
RS232OnReceive( dword port, dword buffer[], dword number )
{
   // works after first RS232Receive !
   // buffer == mybuffer, 1<number<=mysize
}
```
