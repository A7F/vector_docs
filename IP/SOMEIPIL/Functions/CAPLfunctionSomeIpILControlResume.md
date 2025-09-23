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
