# coTfsODChk (Level 2)

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE

## Function Syntax

```plaintext
long coTfsODChk( void );
```

## Description

This function executes a user-defined object dictionary test.

**Test preparation**

The objects which are to test should be added to the internal list of the test objects with the following functions:

- [coTfsODClearAllEntries](CAPLfunctionCoTfsOdClearAllEntries.md)
- [coTfsODAddEntry](CAPLfunctionCoTfsOdAddEntry.md)
- [coTfsODAddOptEntryValue](CAPLfunctionCoTfsOdAddOptEntryValue.md)
- [coTfsODAddOptEntryValueRange](CAPLfunctionCoTfsOdAddOptEntryValueRange.md)
- [coTfsODAddEntryIndexRange](CAPLfunctionCoTfsOdAddEntryIndexRange.md)
- [coTfsODAddEntrySubIndexRange](CAPLfunctionCoTfsOdAddEntrySubIndexRange.md)

With the function [coTfsODSetErrorHandling](CAPLfunctionCoTfsOdSetErrorHandling.md) the behavior in an error case can be defined.

**Test flow**

The function checks every object dictionary entry of existence and size. Additionally, the value is compared with the given value. The compare mask defines which data bits are compared and must be identical.

The complete test is only executed if the access type of the object is not writeOnly.

On a positive comparison and access type readWrite, the read value is written also.

**Test result**

The test was successful if all necessary objects exist and the read values are identical with the defined values. For optional objects, the test node must answer with a SDO abort code (0x08000000, 0x06020000 or 0x06090011) or return a correct value.

If the access type of the object is readWrite, the read value must be writable with a SDO download without error.

## Parameters

—

## Return Values

[Error code](../CAPLfunctionsCANopenNLTFSErrorCodes.md)

## Example

See example of [coTfsODAddEntry](CAPLfunctionCoTfsOdAddEntry.md)
