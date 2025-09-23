[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAllocTableGetCL.md)

**CAPL Functions** » **MOST** » **mostAllocTableGetCL**

# mostAllocTableGetCL

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostAllocTableGetCL(long channel, long idx);
```

## Description

Returns the connection label of the respective entry in the allocation table.

## Parameters

- **channel**: Application channel number.
- **idx**: Index of the entry in the allocation table.

## Return Values

- **\>= 0**: Connection label of the concerning entry.
- **\< 0**: MOST CAPL [error codes](../CAPLfunctionsMOSTErrorCodes.md).

## Example

—
