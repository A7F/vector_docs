# coTfsLssWaitForIdentifySlaveResponse (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssWaitForIdentifySlaveResponse( void );
```

## Description

This function waits for the **Identify slave protocol response** message.

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```c
/* waits for identify slave protocol response message */
if (coTfsLssWaitForIdentifySlaveResponse() == 1) {
  /* waits for LSS identify slave protocol response message */
}
```
