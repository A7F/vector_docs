# coTfsLssWaitForIdentifyNonConfSlaveResponse (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssWaitForIdentifyNonConfSlaveResponse( void );
```

## Description

This function waits for an **Identify non-configured slave** response.

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* wait for identify non configured slave response */
if (coTfsLssWaitForIdentifyNonConfSlaveResponse() == 1) {
  /* response received */
}
```
