[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthILControlResume.md)

[CAPL Functions](../../../CAPLfunctions.md) » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » AREthILControlResume

# AREthILControlResume

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthILControlResume();
```

## Description

Start sending cyclic messages again after [AREthILControlWait](CAPLfunctionAREthILControlWait.md). Application Endpoints and Provided Services do **not** have to be created again.

## Parameters

—

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

```plaintext
on key 'r '
{
  // resume sending messages
  AREthILControlResume();
}
```

[See Also](javascript:void(0);)
- AREthILControlGetStatus
- AREthILControlInit
- AREthILControlResume
- AREthILControlStart
- AREthILControlStop
- AREthILControlWait

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
