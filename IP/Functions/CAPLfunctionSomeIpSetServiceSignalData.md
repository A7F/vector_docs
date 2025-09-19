[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionSomeIpSetServiceSignalData.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » SetServiceSignalData

# SetServiceSignalData

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long SetServiceSignalData(serviceSignal qualifier, byte buffer [], dword bufferLength); // form 1`
- `long SetServiceSignalData(char qualifier [], byte buffer [], dword bufferLength); // form 2`

## Description

Sets the data of a Service Signal.

## Parameters

- **qualifier**: Qualifier of the [Service Signal](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPServiceSignals.md).
- **buffer[]**: Data buffer for the value of the Service Signal.
- **bufferLength**: Length of the data buffer.

## Return Values

- **0**: no error, function successful.
- **-1**: Service Signal not found. No Service Signal matches the qualifier.
- **-3**: Invalid buffer or buffer length. The length of the buffer has to be greater than zero.
- **-4**: No transmitter to send the Signal. This error may occur if no Interaction Layer is found that provides the Signal to be sent.
- **-255**: General error occurred.

## Example

The example shows access to parameter `StringValue`, which is contained in `Event1` of service `Service1` (Major Version 1, Instance ID 2). The service interface is defined in package `PACKAGE1::PACKAGE2` of database `DemoDatabase`.

```plaintext
on key 's'
{
  byte buffer[1] = {0x12};

  SetServiceSignalData(DemoDatabase::PACKAGE1::PACKAGE2::Service1::1::2::Event1::StringValue, buffer, elcount(buffer));
}
```

**Note**: The [service qualifier](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPServiceSignals.md) is specified without a leading `$` sign.

[SetServiceSignal](CAPLfunctionSomeIpSetServiceSignal.md) • [SetServiceSignalString](CAPLfunctionSomeIpSetServiceSignalString.md) • [GetServiceSignalData](CAPLfunctionSomeIpGetServiceSignalData.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
