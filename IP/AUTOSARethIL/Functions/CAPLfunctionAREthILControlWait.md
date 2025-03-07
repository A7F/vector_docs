[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthILControlWait.md)

**CAPL Functions** » [Ethernet](../../CAPLEthernetStartPage.md) » [AUTOSAR Eth IL](../CAPLfunctionsAREthILOverview.md) » AREthILControlWait

# AREthILControlWait

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long AREthILControlWait();
```

## Description

Stops sending cyclic messages.

Application Endpoints and Provided Services are **not** deleted, Service Discovery continues to run. Messages continue to be received by AUTOSAR Eth IL and can be evaluated.

Use [AREthILControlResume](CAPLfunctionAREthILControlResume.md) to send cyclic messages again.

## Parameters

—

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

```plaintext
on key 'w'
{
  // stop sending messages
  AREthILControlWait();
}
```

[See Also](javascript:void(0);)
```markdown