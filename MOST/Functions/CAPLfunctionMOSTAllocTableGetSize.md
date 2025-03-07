# mostAllocTableGetSize

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAllocTableGetSize.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostAllocTableGetSize

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long mostAllocTableGetSize(long channel);
```

## Description

Returns the number of entries (connection labels) in the allocation table.

## Parameters

- **channel**: Application channel number.

## Return Values

- **>= 0**: Number of entries.
- **< 0**: MOST CAPL [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

List all connection labels in the Write Window on change of the allocation table.

```plaintext
OnMostAllocTable()
{
    long numEntries, labelWidth, label, i;
    numEntries = mostAllocTableGetSize(mostEventChannel());
    write("%f s: OnMostAllocTable(): Number of allocated labels: %d", mostEventTimeNs()/1.0e9, numEntries);
    for(i = 0; i < numEntries; ++i)
    {
        write("  Label: %03X  Width: %d", mostAllocTableGetCL(mostEventChannel(), i), mostAllocTableGetWidth(mostEventChannel(), i));
    }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)