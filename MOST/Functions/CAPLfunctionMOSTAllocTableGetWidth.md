[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAllocTableGetWidth.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAllocTableGetWidth

# mostAllocTableGetWidth

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostAllocTableGetWidth(long channel, long idx);
```

## Description

Returns the number of channels of the respective entry (connection label) in the allocation table.

## Parameters

- **channel**: Application channel number.
- **idx**: Index of the entry in the allocation table.

## Return Values

- **> 0**: Number of channels.
- **< 0**: MOST CAPL [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—

[mostAllocTableGetCL](CAPLfunctionMOSTAllocTableGetCL.md) • [mostAllocTableGetSize](#)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
