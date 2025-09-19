# coTfsSetSdoCANid

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsSetSdoCANid( dword sdoClnRxId, dword sdoClnTxId );
```

## Description

With this function the internal CAN identifiers to be used for the SDO tests are set. **All** test functions, which uses SDO access, will use the specified identifiers. This setting will override the application profile specific SDO id settings.

## Parameters

- **sdoClnRxId**: CAN-ID for receive SDOs.
- **sdoClnTxId**: CAN-ID for send SDOs.

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
coTfsSetSdoCANid(0x580, 0x602); // set internal CAN-ID for Rx SDOs to 0x580 and for Tx SDOs to 0x602
```
