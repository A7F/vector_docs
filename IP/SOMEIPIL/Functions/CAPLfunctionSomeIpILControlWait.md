# SomeIpILControlWait

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpILControlWait();
```

## Description

Stops sending cyclic messages.

Application Endpoints and Provided Services are **not** deleted, Service Discovery continues to run. Messages continue to be received by SOME/IP IL and can be evaluated.

Use [SomeIpILControlResume](CAPLfunctionSomeIpILControlResume.md) to send cyclic messages again.

## Parameters

—

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

```plaintext
on key 'w'
{
  // stop sending messages
  SomeIpILControlWait();
}
```

[See Also](javascript:void(0);)
