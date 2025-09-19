# coTfsODChkStdEntries (Level 3)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsODChkStdEntries( void );
```

## Description

The function executes a [standard test](../CAPLfunctionsCANopenNLTFSCoTfsOdChkStdEntriesObjects.md) of the object dictionary.

For a description of the object check, see [coTfsODChkSingleEntry](CAPLfunctionCoTfsOdChkSingleEntry.md).

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

```plaintext
if (coTfsODChkStdEntries() != 1) {
  write("std object dictionary check failed");
} 
else {
  write("std object dictionary check passed");
}
```
