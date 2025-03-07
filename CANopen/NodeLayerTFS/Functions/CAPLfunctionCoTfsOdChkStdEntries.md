[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANopen/NodeLayerTFS/Functions/CAPLfunctionCoTfsOdChkStdEntries.md)

**CAPL Functions** » **CANopen** » **Test Feature Set Node Layer** » **coTfsODChkStdEntries**

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

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)