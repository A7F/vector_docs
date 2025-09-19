[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetAllocTable.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetAllocTable

# mostGetAllocTable

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This functionality is only available for VN2600/VN2610 and OptoLyzer hardware.

## Function Syntax

```plaintext
long mostGetAllocTable(long channel, byte buffer[], long buffersize);
```

## Description

The `mostGetAllocTable()` function copies the MOST Allocation Table (max. 60 bytes) to a local CAPL buffer. It must be verified that the buffer has the required size (buffersize).

The Allocation Table contains the reservation status of the synchronous MOST channels.

## Parameters

- **channel**: Channel of the connected Interface.
- **buffer**: Destination buffer
- **buffersize**: Destination buffer size

## Return Values

See [error codes](../CAPLfunctionsMOSTErrorCodes.md)

## Example

```plaintext
byte allocTable[60];
// copy allocation table to local buffer
mostGetAllocTable(mostGetChannel(), allocTable, elcount(allocTable));
```

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [OnMostAllocTable](../EventProcedures/CAPLfunctionOnMOSTAllocTable.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
