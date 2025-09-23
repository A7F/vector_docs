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
