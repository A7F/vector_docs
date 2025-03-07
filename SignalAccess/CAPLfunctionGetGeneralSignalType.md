[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/SignalAccess/CAPLfunctionGetGeneralSignalType.md)

[CAPL Functions](../CAPLfunctions.md) » [General](../Other/CAPLGeneralStartPage.md) » [Function Overview](../Other/CAPLfunctionsGeneralOverview.md) » GetGeneralSignalType

# GetGeneralSignalType

[Valid for](../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long GetGeneralSignalType(char signalName[])
```

## Description

Determines the general type of a signal, i.e., whether it is a database signal, a service signal, etc.

## Parameters

- **signalName**: The qualified name of the signal. The syntax is `[Channel::][Database name (alias)::][Node::][Message::]Signa;` the order and completeness of the objects from right to left is important. See the example for [getSignal](../Test/Functions/CAPLfunctionGetSignal.md).

## Return Values

- **0**: Signal was not found.
- **1**: Signal is a database signal.
- **2**: Signal is a service signal.

## Example

```plaintext
long SetGenericSignalValue(char signalName[], double value)
{
  signal * sig;
  serviceSignal * serviceSig;
  switch (GetGeneralSignalType(signalName))
  {
    case 1:
      sig = LookupSignal(signalName);
      $sig = value;
      return 1;
    case 2:
      serviceSig = LookupServiceSignal(signalName);
      $serviceSig = value;
      return 1;
    default:
      return 0;
  }
}
```

[lookupSignal](../Other/Functions/CAPLfunctionlookupSignal.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)