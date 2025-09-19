# coTfsODClearAllEntries (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

**Note**  
Before using this function you have to call [coTfsSetNodeId](CAPLfunctionCoTfsSetNodeId.md) to set the internal node ID.

## Function Syntax

```plaintext
long coTfsODClearAllEntries( void );
```

## Description

The function deletes all objects of the internal test object list, which is used by [coTfsODChk](CAPLfunctionCoTfsOdChk.md) and [coTfsODChkNotExist](CAPLfunctionCoTfsOdChkNotExist.md).

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

See example of [coTfsODAddEntry](CAPLfunctionCoTfsOdAddEntry.md)
