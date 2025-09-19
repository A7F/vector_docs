[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTAsRgGetRxTxLog.md)

**CAPL Functions** » **MOST** » **mostAsRgGetRxTxLog**

# mostAsRgGetRxTxLog

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long mostAsRgGetRxTxLog(long regsel, long i); // form 1
long mostAsRgGetRxTxLog(long regsel, long fblockId, long instId); // form 2
```

## Description

The first one returns the logical device address (node address) at position i of the registry. Indexing starts at 0.

The second one returns the logical device address (node address) of the function block. If there is no entry with the given FBlockId and InstId, an error code <0 is returned.

## Parameters

- **regsel**:
  - 1: Local FBlockList
  - 2: Bus registry
- **i**: Position of the registry entry.
- **fblockId**: Function block ID
- **instId**: Instance ID

## Return Values

- **>=0**: Logical device address
- **<0**: See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

—

[mostAsRgGetSize](CAPLfunctionMOSTAsRgGetSize.md) • [OnMostAsRegistry](../EventProcedures/CAPLfunctionOnMOSTAsRegistry.md)

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
