# coTfsLssSendIdentifyNonConfSlaveResponse (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendIdentifyNonConfSlaveResponse( void );
```

## Description

This function sends an **Identify non-configured remote slave** response.

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* sends LSS identify non configured slave protocol response message */

if (coTfsLssSendIdentifyNonConfSlaveResponse() == 1) {
/* message sent */
}
```
