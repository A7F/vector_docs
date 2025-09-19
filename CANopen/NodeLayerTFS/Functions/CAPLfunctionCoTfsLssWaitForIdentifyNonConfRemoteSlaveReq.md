# coTfsLssWaitForIdentifyNonConfRemoteSlaveRequest (Level 2)

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssWaitForIdentifyNonConfRemoteSlaveRequest( void );
```

## Description

This function waits for an **Identify non-configured remote slave** response.

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```c
/* waits for a LSS identify non configured remote slave request */
if (coTfsLssWaitForIdentifyNonConfRemoteSlaveRequest() == 1) {
  /* request received */
}
```
