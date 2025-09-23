[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionSomeIpSetServiceSignalString.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **SetServiceSignalString**

# SetServiceSignalString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long SetServiceSignalString(serviceSignalString qualifier, char buffer []); // form 1`
- `long SetServiceSignalString(char qualifier [], char buffer []); // form 2`

## Description

Sets the string value of a Service Signal. The function automatically appends the respective [byte order mark (BOM)](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPBOM.md) depending on the data type (UTF8 or UTF16).

## Parameters

- **qualifier**: Qualifier of the [Service Signal](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPServiceSignals.md).
- **buffer[]**: Data buffer for the value of the Service Signal.

## Return Values

- **0**: no error, function successful.
- **-1**: Service Signal not found. No Service Signal matches the qualifier.
- **-2**: Wrong Service Signal type. This function may only be used for Service Signals of a string data type.
- **-3**: Invalid buffer.
- **-4**: No transmitter to send the Signal. This error may occur if no Interaction Layer is found that provides the Signal to be sent.
- **-255**: General error occurred.

## Example

```plaintext
on key 's'
{
    SetServiceSignalString(DemoDatabase::PACKAGE1::PACKAGE2::Service1::1::2::Event1::StringValue,"Hello World");
}
```

**Note**: The [service qualifier](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPServiceSignals.md) is specified without a leading `$` sign.

[SetServiceSignal](CAPLfunctionSomeIpSetServiceSignal.md) • [SetServiceSignalData](CAPLfunctionSomeIpSetServiceSignalData.md) • [GetServiceSignalString](CAPLfunctionSomeIpGetServiceSignalString.md)
