[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/VTSystem/Functions/CAPLfunctionVTSOnSerialReceive.md)

**CAPL Functions** » **VT System** » **OnSerialReceive**

# OnSerialReceive

**Valid for**: CANoe DE • CANoe:lite DE

**Note**  
This callback function must be implemented in the CAPL program by the user to get notifications when data has been received on a serial port of a VT7001 module. The callback can be installed using the CAPL function [SerialSetOnReceiveHandler](CAPLfunctionVTSSerialSetOnReceiveHandler.md).

## Method Syntax

```plaintext
void <OnSerialReceive> ( byte buffer[], dword number);
```

## Description

The function is called when data has been received from the assigned VT7001 serial port.

## Parameters

- **buffer**  
  Receive buffer for the assigned VT7001 serial port (set with [SerialReceive](CAPLfunctionVTSSerialReceive.md)). The buffer is only valid within the callback.

- **number**  
  Number of Bytes that have been received.

## Return Values

—

## Example

See example [SerialConfigure](CAPLfunctionVTSSerialConfigure.md)

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)