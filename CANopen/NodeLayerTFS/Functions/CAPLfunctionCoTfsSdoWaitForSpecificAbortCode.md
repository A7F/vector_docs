# coTfsSDOWaitForSpecificAbortCode (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSDOWaitForSpecificAbortCode( dword nodeId, dword sdoAbortCode );
```

## Description

The function waits for receiving the specified SDO abort message of the device or the occurrence of a time-out.

## Parameters

- **nodeId**: Node-ID of the device, 1..127.
- **sdoAbortCode**: SDO abort code.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
dword nodeId = 0x5;

if (coTfsSDOWaitForSpecificAbortCode(nodeId, sdoAbortCode) == 1) {
  write("SDO abort message received");
}
```
