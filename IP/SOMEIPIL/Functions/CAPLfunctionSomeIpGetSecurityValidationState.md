[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpGetSecurityValidationState.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpGetSecurityValidationState

# SomeIpGetSecurityValidationState

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long SomeIpGetSecurityValidationState ( dword messageHandle );
```

## Description

This function returns the Security-Validation-State of a received SOME/IP message.

## Parameters

- **messageHandle**  
  Handle of a received SOME/IP message (e.g. see [OnSomeIpMessage](CAPLfunctionOnSomeIpMessage.md))

## Return Values

- **-1**  
  Message is invalid

- **0**  
  Message is not secured

- **1**  
  Message is valid

- **>1**  
  [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

—
