# coTfsLssSendIdentifySlaveResponse (Level 2)

**Valid for**: CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendIdentifySlaveResponse( void );
```

## Description

This function sends an **Identify slave protocol response** message.

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* sends LSS identify slave protocol response message */

if (coTfsLssSendIdentifySlaveResponse() == 1) {
  /* message sent */
}
```
