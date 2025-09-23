[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionSomeIpGetServiceSignal.md)

**CAPL Functions** » **Ethernet** » **Function Overview** » **GetServiceSignal**

# GetServiceSignal

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `double GetServiceSignal(serviceSignalNumber qualifier); // form 1`
- `long GetServiceSignal(char qualifier [], double& value); // form 2`

## Description

Reads the value of a Service Signal.

## Parameters

- **qualifier**: Qualifier of the [Service Signal](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPServiceSignals.md).
- **value**: Value of the Service Signal is copied to this variable.

## Return Values

- **Return value form 1**: Always the signal value.
- **0**: no error, function successful.
- **-1**: Service Signal not found. No Service Signal matches the qualifier.
- **-2**: Wrong Service Signal type. This function may only be used for Service Signals of a numeric data type.
- **-4**: There is no transmitter for specified Service Signal.
- **-3**: Invalid buffer.
- **-5**: Service Signal has not been observed until now.
- **-255**: General error occurred.

## Example

—

[GetServiceSignalData](CAPLfunctionSomeIpGetServiceSignalData.md) • [GetServiceSignalString](CAPLfunctionSomeIpGetServiceSignalString.md) • [SetServiceSignal](CAPLfunctionSomeIpSetServiceSignal.md)
