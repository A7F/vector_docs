[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionSomeIpGetServiceSignalData.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **GetServiceSignalData**

# GetServiceSignalData

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

- `long GetServiceSignalData(serviceSignal qualifier, byte buffer [], dword bufferLength); // form 1`
- `long GetServiceSignalData(char qualifier [], byte buffer [], dword bufferLength); // form 2`

## Description

Reads the data of a Service Signal.

## Parameters

- **qualifier**: Qualifier of the [Service Signal](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPServiceSignals.md).

- **buffer[]**: Data buffer for the value of the Service Signal.

- **bufferLength**: Length of the data buffer.

## Return Values

- **>=0**: Number of bytes that have been fetched from the Service Signal.

- **-1**: Service Signal not found. No Service Signal matches the qualifier.

- **-3**: Invalid buffer or buffer length. The length of the buffer has to be greater than zero.

- **-5**: Service Signal has not been observed until now.

- **-255**: General error occurred.

## Example

The example shows access to parameter `StringValue`, which is contained in `Event1` of service `Service1` (Major Version 1, Instance ID 2). The service interface is defined in package `PACKAGE1::PACKAGE2` of database `DemoDatabase`.

```plaintext
on key 'r'
{
  byte buffer[255];
  GetServiceSignalData(DemoDatabase::PACKAGE1::PACKAGE2::Service1::1::2::Event1::StringValue, buffer, elcount(buffer));
}
```

**Note**: The [service qualifier](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPServiceSignals.md) is specified without a leading `$` sign.

[GetServiceSignal](CAPLfunctionSomeIpGetServiceSignal.md) • [GetServiceSignalString](CAPLfunctionSomeIpGetServiceSignalString.md) • [SetServiceSignalData](CAPLfunctionSomeIpSetServiceSignalData.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)