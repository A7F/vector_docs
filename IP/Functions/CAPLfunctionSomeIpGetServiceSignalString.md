[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionSomeIpGetServiceSignalString.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **GetServiceSignalString**

# GetServiceSignalString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long GetServiceSignalString(serviceSignalString qualifier, char buffer [], dword bufferLength); // form 1`
- `long GetServiceSignalString(char qualifier [], char buffer [], dword bufferLength); // form 2`

## Description

Reads the string value of a Service Signal.

## Parameters

- **qualifier**: Qualifier of the [Service Signal](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPServiceSignals.md).
- **buffer[]**: Data buffer for the value of the Service Signal.
- **bufferLength**: Length of the data buffer.

## Return Values

- **>=0**: Length of the string that has been fetched from the Service Signal.
- **-1**: Service Signal not found. No Service Signal matches the qualifier.
- **-2**: Wrong Service Signal type. This function may only be used for Service Signals of a string data type.
- **-3**: Invalid buffer or buffer length. The length of the buffer has to be greater than zero.
- **-5**: Service Signal has not been observed until now.
- **-255**: General error occurred.

## Example

```plaintext
on key 'r'
{
  char buffer[255];
  GetServiceSignalString(DemoDatabase::PACKAGE1::PACKAGE2::Service1::1::2::Event1::StringValue, buffer, elcount(buffer));

  write("Actual value of Service Signal StringValue: %s",buffer);
}
```

**Note**: The [service qualifier](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPServiceSignals.md) is specified without a leading `$` sign.

[GetServiceSignal](CAPLfunctionSomeIpGetServiceSignal.md) • [GetServiceSignalData](CAPLfunctionSomeIpGetServiceSignalData.md) • [SetServiceSignalString](CAPLfunctionSomeIpSetServiceSignalString.md)
