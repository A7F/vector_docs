[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpGetLastError.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpGetLastError

# SomeIpGetLastError

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpGetLastError();
```

## Description

This function can be used to check whether the last called function of SOME/IP IL has been successfully executed. The call of this function does **not** reset the saved error.

In the event of an error, a detailed error description can be read out using the [SomeIpGetLastErrorText](CAPLfunctionSomeIpGetLastErrorText.md) function.

## Parameters

—

## Return Values

- **0**: The last called function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

```plaintext
long retVal;

// resume sending messages
SomeIpILControlResume();

// check if last function was executed correct
if((retVal = SomeIpGetLastError()) != 0)
{
  write("SOME/IP IL error occured: Error code: %d", retVal);
} // if
```

[See Also](javascript:void(0);)
- SomeIpGetLastError
- [SomeIpGetLastErrorText](CAPLfunctionSomeIpGetLastErrorText.md#aanchor28396)
- [SomeIpSetProperty](CAPLfunctionSomeIpSetProperty.md#aanchor11923)
- [SomeIpSetVerbosity](CAPLfunctionSomeIpSetVerbosity.md#aanchor2250)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)