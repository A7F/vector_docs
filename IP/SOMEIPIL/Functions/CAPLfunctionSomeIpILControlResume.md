[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpILControlResume.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [SOME/IP IL](../CAPLfunctionsSomeIPILOverview.md) » SomeIpILControlResume

# SomeIpILControlResume

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpILControlResume();
```

## Description

Start sending cyclic messages again after [SomeIpILControlWait](CAPLfunctionSomeIpILControlWait.md). Application Endpoints and Provided Services do **not** have to be created again.

## Parameters

—

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

```plaintext
on key 'r '
{
  // resume sending messages
  SomeIpILControlResume();
}
```

[See Also](javascript:void(0);)
