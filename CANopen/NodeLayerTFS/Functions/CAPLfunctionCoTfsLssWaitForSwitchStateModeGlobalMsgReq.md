# coTfsLssWaitForSwitchStateModeGlobalRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssWaitForSwitchStateModeGlobalRequest( byte[] pMode );
```

## Description

This function waits for a **LSS switch state global mode** request.

## Parameters

- **pMode**: 
  - 0 - waiting mode
  - 1 - configuration mode

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
byte pMode[1];

/* waits for LSS switch state global request */
if (coTfsLssWaitForSwitchStateModeGlobalRequest() == 1) {
  /* received LSS switch state global request */
  /* value in pMode[0] */
}
```
