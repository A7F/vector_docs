[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSOnSerialSend.md)

**CAPL Functions** » **VT System** » **OnSerialSend**

# OnSerialSend

**Valid for**: CANoe DE • CANoe:lite DE

**Note**  
This callback function must be implemented in the CAPL program by the user to get notifications when send operations on a serial port of a VT7001 module have been completed. The callback can be installed using the CAPL function [SerialSetOnSendHandler](CAPLfunctionVTSSerialSetOnSendHandler.md).

## Method Syntax

`void <OnSerialSend> ( byte buffer[], dword number);`

## Description

The function is called when a send operation has been completed on the assigned VT7001 serial port.

## Parameters

- **buffer**: Buffer with the data that has been sent.
- **number**: Number of Bytes that have been sent.

## Return Values

—

## Example

See example [SerialConfigure](CAPLfunctionVTSSerialConfigure.md)
