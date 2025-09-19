# coTfsLssSendSwitchStateModeGlobalRequest (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsLssSendSwitchStateModeGlobalRequest( dword mode );
```

## Description

This function sends a LSS switch state global mode request.

## Parameters

- **mode**  
  0 - switch to waiting mode  
  1 - switch to configuration mode

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
/* send LSS switch state global protocol request -> switch to waiting state (mode = 0) */

if (coTfsLssSendSwitchStateModeGlobalRequest( 0 ) != 1) {
  /* message could not be sent */
}
```
