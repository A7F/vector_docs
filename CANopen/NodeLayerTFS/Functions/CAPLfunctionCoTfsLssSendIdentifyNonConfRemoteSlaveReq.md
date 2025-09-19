# coTfsLssSendIdentifyNonConfRemoteSlaveRequest (Level 2)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendIdentifyNonConfRemoteSlaveRequest( void );
```

## Description

This function sends an **Identify non-configured remote slave** response.

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* send LSS identify non configured remote slave request */

if (coTfsLssSendIdentifyNonConfRemoteSlaveRequest() == 1) {
  /* request sent */
}
```
