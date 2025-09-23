[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/Functions/CAPLfunctionSomeIpSetServiceSignal.md)

[CAPL Functions](../../CAPLfunctions.md) » [Ethernet](../CAPLEthernetStartPage.md) » [Function Overview](../CAPLfunctionsIPOverview.md) » SetServiceSignal

# SetServiceSignal

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
double SetServiceSignal(serviceSignalNumber qualifier, double value); // form 1
double SetServiceSignal(char qualifier [], double value); // form 2
```

## Description

Sets the value of a Service Signal.

## Parameters

- **qualifier**: Qualifier of the [Service Signal](../../../CANoeCANalyzer/Ethernet/ILSomeIP/ILSomeIPServiceSignals.md).
- **value**: Value to be set for the Service Signal.

## Return Values

- **0**: no error, function successful.
- **-1**: Service signal not found. No service signal matches the qualifier.
- **-2**: Wrong service signal type. This function may only be used for service signals of a numeric data type.
- **-4**: No transmitter to send the Signal. This error may occur if no Interaction Layer is found that provides the Signal to be sent.
- **-255**: General error occurred.

## Example

—

[SetServiceSignalData](CAPLfunctionSomeIpSetServiceSignalData.md) • [SetServiceSignalString](CAPLfunctionSomeIpSetServiceSignalString.md) • [GetServiceSignal](CAPLfunctionSomeIpGetServiceSignal.md)
